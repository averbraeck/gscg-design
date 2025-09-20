# 7. Development

Last Updated: 2025-09-21

__Changelog:__
 - 2025-09-21 - Document Creation



## 7.1. Detailed technical choices

In web searches and discussion with AI, several suggestions came up to further finetune the architecture from the previous chapter.

#### 1) Apache httpd in front

- HTTP/2 + Brotli: enable `mod_http2` and `mod_brotli`.<br>
  `H2Direct on`, `H2ModernTLSOnly on`.<br>
  `AddOutputFilterByType BROTLI_COMPRESS text/html text/css application/javascript application/json`.
- Caching: serve `/static/` directly with long Cache-Control (e.g., 30–90 days) + ETag; add a cache-buster in filenames.
- Reverse proxy: prefer `mod_proxy_http` over AJP (Apache JServ Protocol), since it is simpler and safer.<br>
  Keep backend to Tomcat on HTTP/1.1; clients get HTTP/2 from Apache.
- Timeouts/keep-alive: `KeepAlive On` with a sane `KeepAliveTimeout` (2–5 s) and `MaxKeepAliveRequests 100–200`.

*For Brotli, see below.*


#### 2) Tomcat 11 basics

- Thread pool: default ~200 is already fine for 100 users. If blocking DB calls are used, keep it 100–300.
- Compression: if Apache is not used for compression, enable Tomcat gzip; otherwise disable to avoid double work.
- Static offload: map `/static/*` to Apache only; exclude it from Tomcat.
- JSP discipline: EL (Expression Language) + JSTL (JavaServer Pages Standard Tag Library) only; see [https://www.oracle.com/application-development/technologies/jdeveloper/jstl-el-adf.html](https://www.oracle.com/application-development/technologies/jdeveloper/jstl-el-adf.html). Do not use scriptlets as they make the code very unreadable and bug-prone. For complex HTML, keep current approach (server-side generation) or consider a tiny template engine (Pebble/Mustache) for maintainability.


#### 3) Java 21 niceties (optional)

- Virtual threads for blocking tasks: even with Tomcat’s platform-thread request model, DB-heavy/IO work inside handlers can be offloaded to a virtual-thread `ExecutorService` to improve utilization without changing your code style.
- GC: ZGC or G1 both fine. For small-ish heaps, G1 is great; for low-latency spikes, try ZGC.<br>
  Example flags: `-XX:+UseZGC -XX:MaxRAMPercentage=60`.


#### 4) HikariCP + jOOQ
- Pool size: usually `min(32, cores * 2)` is enough. Start with 10–20 for 100 users and watch metrics.
- Timeouts: `connectionTimeout=3s`, `validationTimeout=1s`, `idleTimeout=2–5min`, `maxLifetime=30min` (and keep < MariaDB's `wait_timeout`).
- Fail fast: set `initializationFailTimeout=0` in dev for quick boot, >0 in prod if startup should fail when DB is down.
- jOOQ: keep SQL explicit; add Flyway for schema migrations.

*For Flyway, see below*


#### 5) MariaDB tuning for this load

- `innodb_buffer_pool_size`: 50–70% of RAM allocated to DB node (if DB is dedicated).
- `innodb_flush_log_at_trx_commit=1` for durability (use 2 if you need more throughput and can accept minor risk).
- `max_connections`: slightly above Hikari `maximumPoolSize` + spare (e.g., 100–150).
- `thread_cache_size`: a few dozen helps connection churn.
- Index hot paths and add `EXPLAIN` checks to CI.


#### 6) Frontend without SPA (Single-Page Application) pain

- HTMX for partial updates + progressive enhancement; plays great with JSP/templating.
- Alpine.js for tiny interactivity. Other libraries to consider are Pebble, Tailwind, and ChartJS.
- Streams via SSE for "live-ish" updates; WebSocket only if we truly need bidirectional.

*For HTMX, see below*<br>
*For Alpine.js, see below*<br>
*For Pebble, see below*<br>
*For Tailwind, see below*<br>
*For ChartJS, see below*


#### 7) Security & sessions

- TLS: strong ciphers in Apache; HSTS.
- Cookies: `Secure; HttpOnly; SameSite=Lax/Strict`.
- CSP: at least `default-src 'self'`.
- CSRF: Tomcat filter or a simple token pattern on POST forms.


#### 8) Observability (lightweight)

- Access logs: enable in both Apache (client view) and Tomcat (app view).
- App metrics: Dropwizard Metrics or Micrometer core (no Spring needed). Expose /metrics in plain text or JSON.
- JMX: expose Hikari metrics (active/idle, await time) and track DB time vs render time.


#### 9) Deployment hygiene (no containers required)

- Fat JAR or exploded WAR in Tomcat — whichever is prefered.
- systemd unit for Tomcat (or fat-jar) with `Restart=always` and a reasonable `LimitNOFILE` (e.g., 65535).
- Log rotation: `logrotate` for Apache and app logs.
- Blue/green: two Tomcat instances behind Apache `ProxyPass` + quick swap with `ProxyPassMatch` or a config include.


#### 10) Simple load/perf sanity checks

Check with `wrk`/`ab`/`hey` for:
- median/95p latency under typical and peak bursts,
- CPU saturation point,
- DB connections staying below pool cap,
- GC pauses sub-10ms for the endpoints.



