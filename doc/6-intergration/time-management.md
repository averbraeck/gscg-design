# 6.2. Time management

Last Updated: 2025-09-20

__Changelog:__
 - 2025-09-20 - Document Creation


## 6.2.1. Choice for simulator

The time management choices below assume a central simulation model with one execution thread (see the [federates document](federates.md) for more information).

The time management is taken care of by the [DSOL](https://github.com/averbraeck/dsol) simulator. In order to make time move smoothly, and to have clock times for the player to refer to, the [ClockDevsRealTimeAnimator](https://github.com/averbraeck/dsol/blob/main/dsol-core/src/main/java/nl/tudelft/simulation/dsol/simulators/clock/ClockDevsRealTimeAnimator.java) looks like the best class to take care of time management for the simulation:

- the speed of the simulation can be set as a multiple of wall clock time (e.g., one month of simulation time per minute of wall clock time)
- clock time can be expressed as a date and time for the player, enabling the players to relate the due date of an order to the game time

For now, one central time manager is foreseen. All player panels, actors, and simulation components refer to the central simulation time for the game time. The actors and simulation components are all part of the simulation model that runs on the server. 


## 6.2.2. Issues with player panels

The player panel can have latency in sending information. This means that the timestamp of a message originating from a player panel can only be set in the simulation model running on the server. 

This can, of course, lead to problems. When a player is slowly filling out a screen to react to a request with a cutoff time, the cutoff time can have passed once the player presses 'SEND' or 'SUBMIT'. The central simulation model should therefore be able to handle requests that are:
- pointing to dates and times in the past (e.g., when the player promises a delivery date that has already passed in the simulation)
- referring to information that does not exist in the simulation model anymore (e.g., when a player reacts to a RFQ after the cutoff date)

It is important that the player gets a clear message when these situations occur. 

