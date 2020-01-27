# Finite State Machine pattern

[Wikipedia](https://en.wikipedia.org/wiki/Finite-state_machine)

[Redux pattern](../redux/redux-intro-notes.md)

* Any software you make can be described in a finite number of states (e.g., `idle`, `loading`, `success`, `error`)
* You can only be in one of those states at any given time (e.g., you can’t be in the `success` and `error` states at the same time)
* You always start at some initial state (e.g., `idle`)
* You move from state to state, or transition, based on events (e.g., from the `idle` state, when the `LOAD` event occurs, you immediately transition to the `loading` state)

## Statecharts

* statecharts are [UML state machines](https://en.wikipedia.org/wiki/UML_state_machine)

## Types of finite state machines

* [Mealy machine](https://en.wikipedia.org/wiki/Mealy_machine)
* [Moore machine](https://en.wikipedia.org/wiki/Moore_machine)
