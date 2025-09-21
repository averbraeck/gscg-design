# 6.3. Live components

[Back to Table of Contents](../../README.md)

Last Updated: 2025-09-21

__Changelog:__
 - 2025-09-20 - Document Creation


## 6.3.1. Options for technical front-end architecture

Given the fact that the game is programmed in Java (the simulation and supply chain libraries on which the project builds are also coded in Java), a web technology that fits Java best is to be chosen. A quick overview of architectures from ChatGPT 5.0:

#### Core Web Serving
- Servlets & JSP (Jakarta EE / Tomcat / Jetty)
  The traditional foundation: Servlets handle HTTP requests/responses; JSP can embed Java in HTML. Flexible, but lower-level.
- Jakarta EE / Java EE full stack (GlassFish, WildFly, Payara)
  Standardized enterprise stack with Servlets, JSF, CDI, JAX-RS, and more. Scalable but often heavyweight.

#### Modern Java Frameworks
- Spring Boot / Spring MVC
  The most popular framework for building scalable web apps in Java. Lets you serve HTML pages (via Thymeleaf, FreeMarker, Mustache) or expose REST APIs for a frontend.
- Micronaut / Quarkus / Helidon
  Newer "cloud-native" Java frameworks. Lightweight, very fast startup, designed for microservices and containers. Good for high scalability with less overhead.

#### Templating Engines (for HTML generation)
- Thymeleaf – integrates seamlessly with Spring; HTML-friendly templates.
- FreeMarker – fast, flexible, widely used.
- Mustache / Handlebars – logic-less templating, can be shared with JavaScript frontends.

#### Component-Based Java Web UI
- Vaadin – Java components that render to HTML/JS automatically. Good for rich apps without writing JavaScript.
- Apache Wicket – component-oriented web framework, keeps UI logic in Java.
- JSF (Jakarta Faces) – part of Jakarta EE; declarative UI with server-side components. Legacy in some contexts but still used.

#### APIs + Modern Frontends
A common scalable architecture is:
- Java backend (Spring Boot, Micronaut, Quarkus) provides REST/GraphQL APIs.
- Frontend built with React, Vue, Angular, or Svelte (separate, not Java).
  The frontend consumes JSON data from your Java backend.
  This scales extremely well, as frontend and backend can scale independently.

#### Reactive / Event-driven Web
For very large numbers of concurrent participants (e.g. chat, streaming, collaborative apps):
- Spring WebFlux (reactive programming with Project Reactor)
- Vert.x (event-driven toolkit, polyglot, very scalable)
- Akka HTTP / Play Framework (Scala-based but JVM, integrates well)
These use non-blocking IO to handle many connections efficiently.

#### Deployment & Scalability
- Standalone JAR with embedded server (Spring Boot with Tomcat/Jetty/Undertow).
- Application servers (WildFly, GlassFish, Payara).
- Containers / Kubernetes – standard for scalable deployments.
- Cloud-native frameworks (Quarkus, Micronaut) optimize for serverless/cloud scale.

In this case, we do not need a cloud architecture, as the game will be server-based. It has to scale to several dozen users, not (hundreds of) thousands. So, no cloud architecture (Kubernetes), nor cloud-native solutions. Spring is pretty heavy and has a very steep learning curve. The 'old' Tomcat solution has less overhead and probably works best.


## 6.3.2. Choice of technical front-end architecture

In the end, the choice was made for:
- **MariaDB database**<br>
  This could be any database, but MariaDB is open and a good SQL choice. It also links nicely to the SQL database schemes that were drawn for the [database design](../4-architecture/database-design.md). If necessary, MariaDB can be replaced by any other SQL database without much effort.
- **jOOQ library**<br>
  jOOQ offers SQL syntax in Java, and can automatically generate Java equivalent for the SQL database tables for the game with a script.
- **HikariCP**<br>
  The HihariCP library offers connection pooling for the MariaDB database from Java. This makes the database access faster and more scalable.
- **Apache Tomcat**<br>
  For the servlet, we choose for a traditional, relatively lightweight solution. Overhead from many of the other frameworks is not needed here, since the number of users is relatively limited, and we do not need the extra functions that are offered by some of the newer frameworks. Tomcat is fully serviced, and Tomcat-11 is current and well-maintained.
- **Apache httpd**
  On the server, apache httpd is the front-end that the clients 'see'. using a proxy plus reverse proxy, information from Apache is exchanged with the Tomcat containers that run locally on the server (e.g., on port 8080 or 8081). Apache httpd is robust, scalable, and safe.

