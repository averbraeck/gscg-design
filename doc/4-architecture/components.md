# High-level component breakdown

Last updated: 25-0802925

__Changelog:__
 - 2025-08-25 - Document creation
 - 2025-08-26 - Update of the diagram with clearer communication with the persistence layer
 - 2025-08-26 - Made the data sources consistent with database design document
 - 2025-08-27 - Update architecture diagram: give access to Model Factory for admins and facilitator
 

## Architectural diagram
 
On a very high level, the overall GSCG application looks as follows:

![](diagrams/gscg-architecture.png)

All roles as identified in the use cases interact with the applications through a web page. On the server, several applications (e.g., servlets) are running for the different roles. All data is persisted in one or more databases. Four different data sets are identified:

- GSCG data with the organizational details and users per organization
- Game design data with game definitions and game settings
- Game state data with the persisted game so it can be restarted at a later date or after a crash.
- Game play data for game data analytics (potentially through an external service such as gamedata.nl). 

A rough indication of the simulation itself is given in the diagram as well. The following important components are identified:

- Simulator for time management of the simulation.
- Persistence layer for data management of the simulation.
- Scenario for controlling the way that the game play unfolds.
- Agents 1 through m for automated actions of organizations that are not player-controlled.
- Supply chain organizations 1 through n for actions that are controlled by players.
- User Interface (UI) wrappers to control the organizations by the players.


## Handling of time in the simulation and database

The **Global** Supply Chain Game looks at world-wide trade. This means that different companies operate in different time zones, with different office times. In the game play, these differences are important; placing an order just before or after COB before the weekend can make a big difference in when the goods can be received.

The simulator clock has one central game time, which can probably best be expressed in UTC. Different actors then are in a different time zone + or - a number of hours from UTC. For this reason, the location of an actor has a `timezone_offset` that indicates the number of hours ahead or behind UTC. It is expressed as a double, since not all countries have an integer difference for the number of hours away from UTC.

The following rules apply:
- All timestamps are expressed in UTC, in the global game time.
- When game time is shown to all players, UTC is used.
- When it matters, both UTC and local time can be shown on the screen. 
- Office hours of an actor (or role) are expressed in local time (e.g., 08:00-17:00).

