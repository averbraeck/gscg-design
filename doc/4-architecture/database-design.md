# 4.1. Database design

Last Updated: 2025-08-11

__Changelog:__
 - 2025-08-11 - Document creation


The GSCG database is designed in three layers:

1. **User layer** with the organizations and users and their access rights.
2. **Game Instance layer** with the defined game instances with their actors, parameters, scenarios and player strategies.
3. **Game Session layer** with game sessions, game state, and game results

The results from the game can also be sent to the external data platform [gamedata.nl](https://gamedata.nl).

