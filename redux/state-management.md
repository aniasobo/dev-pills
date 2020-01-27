# State management in Redux

Redux pattern == the [finite state machine](../cs/finite-state-machine.md) 

**Redux state management model** - `state + action = newState`

**State machine model** - `state + event = newState + effects`

Reducers are code representations of this:

```
function userReducer(state, event) {
  // Return the next state, which is
  // determined based on the current `state`
  // and the received `event` object

  // This nextState may contain a "finite"
  // state value, as well as "extended"
  // state values.

  // It may also contain side-effects
  // to be executed by some interpreter.
  return nextState;
}
```

[TREAT REDUCERS AS STATE MACHINES from Docs](https://redux.js.org/style-guide/style-guide/#treat-reducers-as-state-machines)

