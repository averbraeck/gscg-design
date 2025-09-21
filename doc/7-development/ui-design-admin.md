# 7.2. UI Design Admin Panel

[Back to Table of Contents](../../README.md)

Last Updated: 2025-09-21

__Changelog:__
 - 2025-09-21 - Document Creation


The admin panel will be modeled after the gamedata platform, and reuse code of the gamedata project.

Menu choices as a hierarchy are as follows:

**ADMIN**

1. Home
2. Users
   - User
   - Organization Role
   - Game Role
   - Org-Game Role
   - Game Session Role
   - Player Role
3. Organizations
   - Organization
   - Organization Role
   - Organization-Game
   - Org-Game Role
   - Game Session
   - Game Session Role
4. Game
   - Game
   - Game Version
   - Game Role
   - Organization-Game
5. Game Definition
   - Game
   - Game Version
   - Parameter Type
   - Actor Type
   - Actor Parameter
   - Role Type
   - Role Parameter
   - Handler Type
   - Handler Param
   - Process Type
   - Process Param

**GAME DESIGN**

6. Product
   - Game
   - Game Version
   - SKU
   - Product
   - Bill of Materials
   - BOM Item
7. Actor-Role
   - Game
   - Game Version
   - Actor
   - Actor Param Value
   - Role
   - Role Param Value
   - Location
   - Landmass
   - Content Receiver
8. Handler & Process
   - Game
   - Game Version
   - Actor
   - Role
   - Handler
   - Handler Value
   - Valid Actor Type
   - Valid Actor
   - Valid Product
   - Process
   - Process Value
9. Transport
   - Game
   - Game Version
   - Transport Mode
   - SKU
   - Handled SKU
   - Landmass
   - Location
   - Transfer
10. Scenario
    - Game
    - Game Version
    - Game Scenario
    - Event
    - Trigger Fixed
    - Trigger Interval
    - News Message
    - Actor
    - News Actor
    - News Actor Type
11. Goals & Strategies
    - Game
    - Game Version
    - Goal
    - Game Version Goal
    - Strategy Category
    - Strategy
    - Strategy List
    - Page List
    - List Page
    - Page

**GAME SESSION**

12. Game Session
    - Game
    - Game Version
    - Game Session
    - Player
    - Goal
    - Game Session Goal
    - Strategy Category
    - Strategy
    - Strategy List
    - Page List
    - List Page
    - Page
13. Player Scores
    - Game
    - Game Version
    - Game Session
    - Player
    - Player scores
    - Session Graphs

**GAME PLAY**

14. Game Analysis
    - Game
    - Game Version
    - Game Session
    - Triggered Event
    - Extra Event
    - Triggered News
    - Extra News
    - Triggered Process
    - Chosen Strategy
    - Player Decision
    - Player Score
    - Chat Message
    - Sent Content
15. Errors
    
**SETTINGS**

16. Settings
17. Logoff

