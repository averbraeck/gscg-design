# GSCG Requirements

Last Updated: 2025-04-30

__Changelog:__
 - 2025-04-30 - Document Creation
 
## 0. Legend
The requirements are numbered respective to the use case from the document ['use-cases'](../1-use-cases/use-cases.md). The requirements are divided into Functional requirements, indicated with an abbreviation "F", and non-functional requirements, indicated with the abbreviation "NF". The requirements are categorized into two classes from the MoSCoW-framework, the "Must-haves", with the letter "C" for "constraint", and the "Should-haves", with the letter "O" for "objective". Combinations are, e.g. NFC2.3, indicating the third requirement for use-case 2, being a non-functional constraint (a must-have). All requirements are consecutively numbered within the use case. 
 
## 1. Portal administration
- FC1.1 The portal administrator must be able to change the password to enter the GSCG portal
- FC1.2 The portal administrator must be able to create a new game instance
- FC1.3 The portal administrator must be able to delete a game instance that has not yet been played
- FC1.4 The portal administrator must be able to create a user
- FC1.5 The portal administrator must be able to delete a user
- FC1.6 The portal administrator must be able to reset the password of a user
- FC1.7 The portal administrator must be able to change the access rights of a user (* see below)
- FC1.8 The portal administrator must be able to create an organization
- FC1.9 The portal administrator must be able to delete an organization (or to disallow access for users of the organization)

Note for FC1.7: The access rights for a user are:
- super-administrator
- organization administrator, with a link to one or more organizations
- organization member, with a link to one or more organizations
- game administrator, with a link to one or more game instances
- game member, with a link to one or more game instances
- session administrator, with a link to one or more game sessions
- session facilitator, with a link to one or more game sessions
- game player, with a link to one or more game sessions

