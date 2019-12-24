# React hooks <!-- omit in toc -->

[Code snippets](https://github.com/30-seconds/30-seconds-of-react)

* allow you to use/define state within a function component (eliminate the need for class components)
* can mimic the behaviour of component lifecycle methods
* start at version `16.8` of React
* import them from `react` in `{}` as you would the `Component` module: `import React, { useState } from 'react';`
* only call hooks on the top level - never inside loops, conditions or nested functions
* never call hooks from non-react-component JS functions

- [useState()](#usestate)
- [useEffect()](#useeffect)
- [useContext()](#usecontext)
- [useReducer()](#usereducer)
- [useMemo()](#usememo)
- [Custom hooks](#custom-hooks)
- [Sources](#sources)
- [Tools](#tools)

---

## `useState()`

* called inside a function to add local state to it
* state is preserved between renders
* returns two values: the current value of state and a function that lets you update it; this funciton can be called from an event handler or elsewhere
* takes one argument: initial state
* state doesn't have to be an object
* can be used more than once within a component, but the calls are made in the same order on every render

## `useEffect()`

* lets you perform the side effects from a function component (ones that can't be done during rendering)
* serves the same purpose as `componentDidMount()` and `componentDidUpdate()` and `componentWillUnmount()`
* tells react to run the side-effect function after updating the DOM
* effects have access to the props and state of the component
* option to tell effects how to clean up post-render
* can be used for multiple effects within the component
* pass an empty array in as second argument to stop the effect getting called again on component update
* non-empty array: contains variables to watch, becasue the hook depends on them; the hook will run again if one of those changes (for example, `[query]` when you're using an input for a search query that gets called - see link below)
* [fetch data inside useEffect()](https://www.robinwieruch.de/react-hooks-fetch-data)

## `useContext()`

* lets you subscribe to React context without introducing nesting or passing down props
* context seems to have to be set with `React.setContext()` and then imported?
* [intro for how to use](https://react.christmas/2019/7)

## `useReducer()`

* lets you manage local state of complex components with a reducer
* a reducer is a pure function that takes a state and returns a new state:

```
const dataFetchReducer = (state, action) => {
  switch (action.type) {
    case 'FETCH_INIT':
      return { ...state };
    case 'FETCH_SUCCESS':
      return { ...state };
    case 'FETCH_FAILURE':
      return { ...state };
    default:
      throw new Error();
  }
};
```

* provide action types and optional payloads to end up with predictable state changes ([as explained here](https://www.robinwieruch.de/react-hooks-fetch-data))

## `useMemo()`

* [good example use with API](https://github.com/karlhadwen/newsreader)
* returns a memoized value
* takes a 'create' function and an array of dependencies
* the memoized value only gets recomputed on change to one of the passed dependencies
* helps avoid expensive recalculations on render
* the function passed into it runs on render; side effects belong in `useEffect()`
* ifno array is given, a new value will be computed on every render
* use it to optimise performace of code that should run ok without it


## Custom hooks

* replace higher-order components and `render props`
* reuse stateful logic, not state itself
* never use the same custom hook twice in a component - because each call to a custom hook has a completely isolated state
* > Custom Hooks are more of a convention than a feature. If a function’s name starts with ”use” and it calls other Hooks, we say it is a custom Hook.
* [Custom Hooks explainer from React Christmas 2019](https://react.christmas/2019/13)

## Sources

* [Docs](https://reactjs.org/docs/hooks-overview.html)
* [Hooks API reference](https://reactjs.org/docs/hooks-reference.html)
* [State hook docs](https://reactjs.org/docs/hooks-state.html)
* [Intro video](https://reactjs.org/docs/hooks-intro.html)

## Tools

* [SWR - React hooks for remote data fetching](https://swr.now.sh/)
