# 4.1. Database design

Last Updated: 2025-08-26

__Changelog:__
 - 2025-08-11 - Document creation
 - 2025-08-26 - Update with more detail about the data layers
 - 2025-08-26 - Made the terminology consistent with the architecture document


## High-level database design

The GSCG database is designed in three separate 'compartments' that are related, but managed by different roles:

1. **GSCG Admin data** with the organizations and users and their access rights.
2. **Game Design data** with the defined game instances with their actors, parameters, scenarios and player strategies.
3. **Game State data** with game sessions, game state, and game results

The results from the game can also be sent to the external data platform [gamedata.nl](https://gamedata.nl). In a sense, this defines a fourth layer:

4. **Game Play data** with game sessions, game state, and game results

