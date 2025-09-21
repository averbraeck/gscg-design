# 2. GSCG Use Cases

[Back to Table of Contents](../../README.md)

Last Updated: 2025-09-21

__Changelog:__
 - 2025-04-03 - Document Creation
 - 2025-04-29 - First set of use cases added
 - 2025-04-30 - Added display map function: [Issue #6](https://github.com/averbraeck/gscg-design/issues/6).
 - 2025-04-30 - Added display functionality: [Issue #5](https://github.com/averbraeck/gscg-design/issues/5). 
 - 2025-04-30 - Added 'Pause game': [Issue #4](https://github.com/averbraeck/gscg-design/issues/4). 
 - 2025-04-30 - Added "Administrator" role according to [Issue #3](https://github.com/averbraeck/gscg-design/issues/3). 
 - 2025-04-30 - Include options for "show scores" activity
 - 2025-05-01 - Strategy setting by player: [Issue #11](https://github.com/averbraeck/gscg-design/issues/11).
 - 2025-05-01 - Login/logout to the portal: [Issue #10](https://github.com/averbraeck/gscg-design/issues/10).
 - 2025-05-01 - Registration for game sessions: [Issue #9](https://github.com/averbraeck/gscg-design/issues/9).
 - 2025-05-01 - Removed labels on the arrows: [Issue #13](https://github.com/averbraeck/gscg-design/issues/13).
 - 2025-05-01 - Added export functions to analytics: [Issue #8](https://github.com/averbraeck/gscg-design/issues/8).
 - 2025-05-01 - Added communication function: [Issue #7](https://github.com/averbraeck/gscg-design/issues/7).
 - 2025-05-01 - Define allowable player strategies: [Issue #12](https://github.com/averbraeck/gscg-design/issues/12).
 - 2025-08-13 - Add chapter number for SE-step "2" to the headers in the document
 - 2025-08-26 - Add missing function in use case diagram for game design (consistency with requirements)
 - 2025-08-29 - Improve clarity of game terms in use cases [Issue #21](https://github.com/averbraeck/gscg-design/issues/21).
 - 2025-08-29 - Re-allocate tasks for session admin and facilitator [Issue #24](https://github.com/averbraeck/gscg-design/issues/24).
 - 2025-08-30 - Allow facilitator to set player self registration [Issue #26](https://github.com/averbraeck/gscg-design/issues/26).
 - 2025-09-18 - Add explanation of game data analysis use case [Issue #39](https://github.com/averbraeck/gscg-design/issues/39).
 - 2025-09-18 - Add explanation of 'game version' in game design [Issue #40](https://github.com/averbraeck/gscg-design/issues/40).
 
 
## 2.1. Portal administration
Portal administration takes care of creating (super) users, designing organizations, and allocating roles such as game designers or session administrators. In portal administration, new games can be created as well, and unused games can be deleted.

![](diagrams/portal-administration.svg)
 
 
## 2.2. Game design
In game design, the actual game play of the game instance is determined. This is done by making a specific version of the game that contains parameters that determine the game play and game experience for the players (events, included actors, map, scenarios, etc.). 
 
![](diagrams/game-design.svg)


## 2.3. Organization administration
Organization administration takes care of creating users for their organization, and allocating roles such as session administrators or facilitators.

![](diagrams/organization-administration.svg)


## 2.4. Session administration
Session administration takes care of defining the details for a new game session (game play) and allocating facilitators. It is possible to set self registration for users, or to define users beforehand.

![](diagrams/session-administration.svg)


## 2.5. Session facilitation
Session facilitation takes care of starting, pausing and stopping of the game, as well as defining game speed. Briefing and debriefing are part of the facilitation. Facilitators can trigger pre-defined actions in the game, and they can communicate with the players. Note that the game can be played in a completely distributed setting, where a built-in communication function can be of use.

![](diagrams/session-facilitation.svg)


## 2.6. Game play
In game play, players are able to register for the game, or log on when they have a pre-defined user account. The players study the briefing before the game, and the debriefing after the game play. During game play, players are shown the pre-defined information such as events, news, as well as dynamic state information. The most important role for the players is to set their strategy, and to make decisions that they enter into the platform. Players can communicate with other players, since the game can be played in a completely distributed setting.

![](diagrams/game-play.svg)


## 2.7. Game data analysis
A game data analyst analyzes the data that is stored about one or more game sessions, either in the application itself, or by exporting data to files. Five categories of data are distinguished: 
- game events (either pre-programmed or injected by the facilitator)
- player events (e.g., every time a player makes a decision or clicks)
- player scores (score development over time or final scores per player)
- log data (anything that is logged to the data storage as log information; could contain technical information about the platform)
- errors (recoverable or non-recoverable errors that can help to increase the stability of the platform)

![](diagrams/game-data-analysis.svg)


