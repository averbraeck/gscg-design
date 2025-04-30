# GSCG Requirements

Last Updated: 2025-04-30

__Changelog:__
 - 2025-04-30 - Document Creation
 
## 0. Legend
The requirements are numbered respective to the use case from the document ['use-cases'](../1-use-cases/use-cases.md). The requirements are divided into Functional requirements, indicated with an abbreviation "F", and non-functional requirements, indicated with the abbreviation "NF". The requirements are categorized into two classes from the MoSCoW-framework, the "Must-haves", with the letter "C" for "constraint", and the "Should-haves", with the letter "O" for "objective". Combinations are, e.g. NFC2.3, indicating the third requirement for use-case 2, being a non-functional constraint (a must-have). All "F" and "HF" requirements are consecutively numbered within the use case, both starting with number 1. 


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
- FC1.8 The portal administrator must be able to create an organization
- FC1.9 The portal administrator must be able to delete an organization (or to disallow access for users of the organization)
- FC1.10 The portal administrator must be able to allocate a user to be the administrator of an organization

Non-functional requirements:
- NFC1.1 The portal administration must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO1.2 The portal administration should run smoothly without noticeable delays
- NFO1.3 The portal administration should have an intuitive interface
- NFO1.4 The portal administration should give clear errors to the portal administrator in case actions are not permitted
- NFO1.5 The portal administration should use a responsive UI to scale to the device preoperties 

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
> Note for NFO1.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on sceens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


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

Non-functional requirements:
- NFC2.1 The game design must run in any modern browser (Chrome, Edge, Firefox, Brave, Safari, Opera)
- NFO2.2 The game design should run smoothly without noticeable delays
- NFO2.3 The game design should have an intuitive interface
- NFO2.4 The game design should give clear errors to the game administrator in case actions are not permitted
- NFO2.5 The game design should use a responsive UI to scale to the device preoperties 

> [!NOTE]
> Note for NFO1.5: it is not required to scale all the way down to a mobile device. The GSCG game is expected to run on sceens with a size of at least 1024x768 pixels, and usually 1920x1080 or better.


