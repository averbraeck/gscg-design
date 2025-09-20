# 7.1. Federates

There are two major options with variants how to set-up the internal architecture of simulation components. These will be discussed below, with their advantages and disadvantages.


## 7.1.1. Central simulation model

The old setup of GSCG had a central simulation model. This means one clock, and one shared state. The big advantage is simplicity: starting the model involves one action, and there is one point of contact for the player clients. The big disadvantage is robustness or resilience. One exception in a relatively unimportant part of the simulation can end the game for all players. 

The architecture roughly looks as follows:

![](diagrams/central-simulation-model.png)

In essence, this leads to a single-threaded simulation. Only one event of each Actor is executed at a time. There is no parallel execution of simulation events. This does keep the simulation simple, since causality and a strict ordering of the time of executed events is always guaranteed. Speed is, however, suffering from this setup, since multiple processors are not used for the execution of the simulation.

Since player events and facilitator events are injected into the game through the player servlet and facilitator servlet in a separate thread, extra care has to be taken when the events from players and facilitators are injected into the game. The UI wrappers for the players and the facilitator wrapper need to use a message queue mechanism that is polled by the simulation to ensure that the simulator dictates when the player events and facilitator events are executed.

This leads to the following execution of the simulation model, in pseudo code, where polling is scheduled as a simulation event:

```
void build() {
  simulator.initialize()
  modelFactory.buildSimulation()
  simulator.scheduleEventRel(pollTime, () -> pollUI())
  simulator.start()
}

void pollUI() {
  for (externalData : facilitator.messageQueue)
    process(externalData)
  for (player : players)
    for (externalData : player.messageQueue)
      process(externalData)
  simulator.scheduleEventRel(pollTime, () -> pollUI())
}
```

In this way, by polling events from the UI, all player and facilitator actions are neatly interleaved between the simulation events from the agents, autonomous processes, scenario events, and player-triggered processes. 



