# GSCG Requirements

Last Updated: 2025-05-01

__Changelog:__
 - 2025-05-01 - Define allowable player strategies: [Issue #12](https://github.com/averbraeck/gscg-design/issues/12).
 - 2025-05-01 - Strategy setting by player: [Issue #11](https://github.com/averbraeck/gscg-design/issues/11).
 - 2025-05-01 - Login/logout to the portal: [Issue #10](https://github.com/averbraeck/gscg-design/issues/10).
 - 2025-05-01 - Registration for game sessions: [Issue #9](https://github.com/averbraeck/gscg-design/issues/9).
 - 2025-05-01 - Added export functions to analytics: [Issue #8](https://github.com/averbraeck/gscg-design/issues/8).
 - 2025-05-01 - Added communication function: [Issue #7](https://github.com/averbraeck/gscg-design/issues/7).
 - 2025-04-30 - Added display map function: [Issue #6](https://github.com/averbraeck/gscg-design/issues/6).
 - 2025-04-30 - Added 'Pause game': [Issue #4](https://github.com/averbraeck/gscg-design/issues/4). 
 - 2025-04-30 - Document Creation
 
## 0. Legend
The requirements are numbered respective to the use case from the document ['use-cases'](../1-use-cases/use-cases.md). The requirements are divided into Functional requirements, indicated with an abbreviation "F", and non-functional requirements, indicated with the abbreviation "NF". The requirements are categorized into two classes from the MoSCoW-framework, the "Must-haves", with the letter "C" for "constraint", and the "Should-haves", with the letter "O" for "objective". Combinations are, e.g. NFC2.3, indicating the third non-functional requirement for use-case 2, being a constraint (a must-have). All "F" and "NF" requirements are consecutively numbered within the use case, both starting with number 1. 


## 1. Portal administration

Functional requirements:
- FC1.1 The portal administrator must be able to change their own password to enter the GSCG portal
- FC1.2 The portal administrator must be able to create a user
- FC1.3 The portal administrator must be able to delete a user
- FC1.4 The portal administrator must be able to reset the password of a user
- FC1.5 The portal administrator must be able to change the access rights of a user (* see below)
- FC1.6 The portal administrator must be able to create a new game instance
- FC1.7 The portal administrator must be able to delete a game instance that has not yet been played
- FC1.8 The portal administrator must be able to allocate a user to be the administrator of a game instance
- FC1.9 The portal administrator must be able to create an organization
- FC1.10 The portal administrator must be able to delete an organization (or to disallow access for users of the organization)
- FC1.11 The portal administrator must be able to allocate a user to be the administrator of an organization
- FC1.12 The portal administrator must be able to login to the portal
- FC1.13 The portal administrator must be able to logout from the portal

Non-functional requirements:
- NFC1.1 The portal administration must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO1.2 The portal administration should run smoothly without noticeable delays
- NFO1.3 The portal administration should have an intuitive user interface
- NFO1.4 The portal administration should give clear errors to the portal administrator in case actions are not permitted
- NFO1.5 The portal administration should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for FC1.5: The access rights for a user are:
> - super-administrator
> - organization administrator, with a link to one or more organizations
> - organization member, with a link to one or more organizations
> - game administrator, with a link to one or more game instances
> - game member, with a link to one or more game instances
> - session administrator, with a link to one or more game sessions
> - session facilitator, with a link to one or more game sessions
> - game player, with a link to one or more game sessions

> [!NOTE]
> Note for NFO1.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


## 2. Game design

- FC2.1 The game designer must be able to change their own password to enter the GSCG portal
- FC2.2 The game designer must be able to create a game instance
- FC2.3 The game designer must be able to clone a game instance
- FC2.4 The game designer must be able to choose a game instance to maintain
- FC2.5 The game designer must be able to set the player goals for the chosen game instance
- FC2.6 The game designer must be able to set the actors to use for the chosen game instance
- FC2.7 The game designer must be able to set the scenario to use for the chosen game instance
- FC2.8 The game designer must be able to set the parameters for an actor in the chosen game instance
- FC2.9 The game designer must be able to set the parameters for a scenario in the chosen game instance
- FO2.10 The game design should present one or more screens that provide an overview of the defined actors with their capabilities
- FO2.11 The game design should present a timeline with the scenario events for the game instance
- FO2.12 The game design should present a map with the actors displayed at their locations
- FC2.13 The game designer must be able to login to the portal
- FC2.14 The game designer must be able to logout from the portal
- FC2.15 The game designer must be able to set allowable strategies that can be chosen by the players

Non-functional requirements:
- NFC2.1 The game design must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO2.2 The game design should run smoothly without noticeable delays
- NFO2.3 The game design should have an intuitive user interface
- NFO2.4 The game design should give clear errors to the game designer in case actions are not permitted
- NFO2.5 The game design should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for NFO2.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


## 3. Organization administration

- FC3.1 The organization administrator must be able to change their own password to enter the GSCG portal
- FC3.2 The organization administrator must be able to create a user
- FC3.3 The organization administrator must be able to delete a user
- FC3.4 The organization administrator must be able to reset the password of a user
- FC3.5 The organization administrator must be able to change the access rights of a user (* see below)
- FC3.6 The organization administrator must be able to change the description of the organization
- FC3.7 The organization administrator must be able to change the logo of the organization
- FC3.8 The organization administrator must be able to allocate existing platform users to the organization
- FO3.9 The organization administration should present an overview of the games in use
- FO3.10 The organization administration should present an overview of the defined game sessions
- FO3.11 The organization administration should present an overview of the users allocated to the organization
- FC3.12 The organization administrator must be able to login to the portal
- FC3.13 The organization administrator must be able to logout from the portal

Non-functional requirements:
- NFC3.1 The organization administration must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO3.2 The organization administration should run smoothly without noticeable delays
- NFO3.3 The organization administration should have an intuitive user interface
- NFO3.4 The organization administration should give clear errors to the organization administrator in case actions are not permitted
- NFO3.5 The organization administration should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for FC3.2 through 3.5: The users that can be maintained are:
> - organization member (for the own organization)
> - session administrator, with a link to one or more game sessions
> - session facilitator, with a link to one or more game sessions
> - game player, with a link to one or more game sessions

> [!NOTE]
> Note for NFO3.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


## 4. Session administration

- FC4.1 The session administrator must be able to change their own password to enter the GSCG portal
- FC4.2 The session administrator must be able to create a user
- FC4.3 The session administrator must be able to delete a user
- FC4.4 The session administrator must be able to reset the password of a user
- FC4.5 The session administrator must be able to change the access rights of a user (* see below)
- FC4.6 The session administrator must be able to create a game session
- FC4.7 The session administrator must be able to change the dates of a game session
- FC4.8 The session administrator must be able to delete a game session that has not yet been played
- FC4.9 The session administrator must be able to allocate users to a game instance
- FC4.10 The session administrator must be able to turn on user self registration for a game session
- FC4.11 The session administrator must be able to generate a batch of anonymous users with login codes and passwords
- FO4.12 The session administration should present an overview of the sessions with dates and play status
- FO4.13 The session administration should present an overview of the facilitators and players allocated to a session
- FC4.14 The session administrator must be able to login to the portal
- FC4.15 The session administrator must be able to logout from the portal
- FC4.16 The session administrator must be able to set or change the allowable strategies that can be chosen by the players

Non-functional requirements:
- NFC4.1 The session administration must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO4.2 The session administration should run smoothly without noticeable delays
- NFO4.3 The session administration should have an intuitive user interface
- NFO4.4 The session administration should give clear errors to the session administrator in case actions are not permitted
- NFO4.5 The session administration should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for FC4.2 through 4.5: The users that can be maintained are:
> - session facilitator, with a link to a game session
> - game player, with a link to a game session

> [!NOTE]
> Note for NFO4.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


## 5. Session facilitation

- FC5.1 The session facilitator must be able to change their own password to enter the GSCG portal
- FC5.2 The session facilitator must be able to create a player for the game session
- FC5.3 The session facilitator must be able to delete a player for the game session
- FC5.4 The session facilitator must be able to reset the password of a user allocated to the game session
- FC5.5 The session facilitator must be able to change the access rights of a player for the game session
- FC5.6 The session facilitator must be able to allocate an existing user to the game session
- FC5.7 The session facilitator must be able to deallocate an existing user from the game session
- FO5.8 The session facilitator should provide a briefing of the game to the players
- FC5.9 The session facilitator must be able to start the game session
- FC5.10 The event of starting the game session must be sent to the gamedata platform
- FC5.11 The session facilitator must be able to change the game speed
- FC5.12 The session facilitator must be able to pause the game
- FO5.13 The session facilitator should be able to insert an extra news item for the players
- FC5.14 The event of adding a news item to the the game session must be sent to the gamedata platform
- FO5.15 The session facilitator should be able to add an intervention into the game
- FC5.16 The event of adding an intervention to the the game session must be sent to the gamedata platform
- FO5.17 The session facilitator should be able to trigger an existing manual intervention during gameplay
- FC5.18 The event of triggering an existing intervention during the the game play must be sent to the gamedata platform
- FO5.19 The session facilitation should present an overview of the players allocated to a session
- FO5.20 The session facilitation should present a map with the actors displayed at their locations
- FO5.21 The session facilitation should allow chatting with the active players in the game session
- FC5.22 The session administrator must be able to login to the portal
- FC5.23 The session administrator must be able to logout from the portal

Non-functional requirements:
- NFC5.1 The session facilitation must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO5.2 The session facilitation should run smoothly without noticeable delays
- NFO5.3 The session facilitation should have an intuitive user interface
- NFO5.4 The session facilitation should give clear errors to the session facilitator in case actions are not permitted
- NFO5.5 The session facilitation should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for NFO5.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


## 6. Game play

- FC6.1 The player must be able to create a userid/password for the game session in case the game allows self-registration
- FC6.2 The player must be able to change their password
- FC6.3 The player must be able to login to the game session with a userid and password
- FO6.4 The game play platform should show the briefing (note that the game might take place in a distributed setting)
- FC6.5 The game play platform must show dynamic state information about the player's firm during game play
- FC6.6 The game play platform must show the news at the correct times during game play
- FC6.7 The player must be able to enter decisions into the game play platform during game play
- FC6.8 The game play platform must send player decisions to the gamedata platform
- FC6.9 The game play platform must show the scores to the player during and after game play
- FO6.10 The game play platform should show the debriefing (note that the game might take place in a distributed setting)
- FC6.11 The player must be able to logout from the game session
- FO6.12 The game play platform should show a map with the actors displayed at their locations, highlighting the player
- FO6.13 The game play platform should allow chatting with other players in the game session and with the facilitator
- FC6.14 The player must be able to define a strategy, dependent on the settings in the game
- FC6.15 The player must be able to motivate their chosen strategy
- FC6.16 The game play platform must send the strategy and the motivation of the player to the gamedata platform

Non-functional requirements:
- NFC6.1 The game play must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO6.2 The game play should run smoothly without noticeable delays
- NFO6.3 The game play should have an intuitive user interface
- NFO6.4 The game play should give clear errors to the player in case actions or decisions are not permitted
- NFO6.5 The game play application should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for NFO6.5: Also for players, it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on screens with a size of at least 1024x768 pixels, and usually 1920x1080 or better. Tests for tablets, Chromebooks, and other devises that students bring to class might be necessary.


## 7. Game data analytics

- FC7.1 The data analyst must be able to login to the game data platform
- FC7.2 The data analyst must be able to change their password
- FC7.3 The data analyst must be able to logout from the game data platform
- FC7.4 The data analyst must be able to choose a game to analyze or export
- FC7.5 The game data platform must show the session and facilitator events for a game session to the data analyst
- FC7.6 The game data platform must show the player events for a game session to the data analyst
- FC7.7 The game data platform must show the player scores for a game session to the data analyst
- FC7.8 The game data platform must show the log data for a game session to the data analyst
- FC7.9 The game data platform must show the errors for a game session to the data analyst
- FC7.10 The game data platform must export the session and facilitator events for a game session to a file
- FC7.11 The game data platform must export the player events for a game session to a file
- FC7.12 The game data platform must export the player scores for a game session to a file
- FC7.13 The game data platform must export the log data for a game session to a file
- FC7.14 The game data platform must export the errors for a game session to a file

Non-functional requirements:
- NFC7.1 The game data platform must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO7.2 The game data platform should run smoothly without noticeable delays
- NFO7.3 The game data platform should have an intuitive user interface
- NFO7.4 The game data platform should have a responsive UI to scale to the device properties 

> [!NOTE]
> Note for NFO7.4: it is not required to scale all the way down to a mobile device. The gamedata platform is expected to run on screens with a size of at least 1920x1080 pixels or better.
