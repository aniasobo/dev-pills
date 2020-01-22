# Notes from intro to Redux

* Redux is a **state manager** that helps organize the flow of data in React applications in a predictable way
* The **Redux Store** is a single object that can represent all of the backing data for a React application
* **Actions** are objects that contain information that pass data around the Redux application
* Action creators construct action objects
* **Reducers** respond to actions and provide ways to update the store
* `React-Router` uses components like the `BrowserRouter`, `Switch`, and `Route` to set up endpoints on the application that link to specific components


## What is Redux

```
Action => Reducer(s) => Store => View => User Interaction => Action ...
```

Redux is a state container (object) which holds state; with an API that enables you to:

* manipulate the state
* receive the state
* listen to state changes

[Hooks from react-redux](../react/hooks.md)

### Notes from the Redux meeting (unedited):

* action, reducer, saga, selector - for each model?
* keep `ACTION_TYPES` in one file
* `dispatch` is a Redux function - a helper that lets you know the store will be altered?
* explicitly set the keys in your store when using a reducer - so they don't null out
* WORKER SAGAS: handle side-effects; generator functions: `function*` (often handle functions) - side-effect functions; make API calls, use the `yield` keyword; allows you to test those in isolation; specific sagas only listen for specific events, call specific APIs; `call()` and `put()` let you call other Redux actions within the sagas
* DOM element (button) - click, action is called, lets reducer know change of state, a saga is listening to this change of state, calls an API, depending on what's returned from the API it calls a specific action, which again tells reducer to update state
* actions dispatched produce timestamp in console, show states to compare
* Redux store chrome extension - adds a Redux tab to the chrome dev tools inspector
* SELECTORS - to get data out of the Redux store; `reselect` library (`import { createSelector } from 'reselect';`); memoises the data - fetched once, it stays cached so it loads quicker whenever you need it; syntax/convention: function names start with `get`; stops you from exposing all the data in the `props` which can be viewed in console - only expose the data that is relevant in given view
