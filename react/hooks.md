# React hooks <!-- omit in toc -->

* allow you to use/define state within a function component (eliminate the need for class components)
* can mimic the behaviour of component lifecycle methods
* start at version `16.8` of React
* import them from `react` in `{}` as you would the `Component` module: `import React, { useState } from 'react';`
* only call hooks on the top level - never inside loops, conditions or nested functions
* never call hooks from non-react-component JS functions

- [`useState()`](#usestate)
- [`useEffect()`](#useeffect)
- [`useContext()`](#usecontext)
- [`useReducer()`](#usereducer)
- [Custom hooks](#custom-hooks)
- [Sources](#sources)

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

## `useContext()`

* lets you subscribe to React context without introducing nesting

## `useReducer()`

* lets you manage local state of complex components with a reducer

## Custom hooks

* replace higher-order components and `render props`
* reuse stateful logic, not state itself
* never use the same custom hook twice in a component - because each call to a custom hook has a completely isolated state
* > Custom Hooks are more of a convention than a feature. If a function’s name starts with ”use” and it calls other Hooks, we say it is a custom Hook.

## Sources

* [Docs](https://reactjs.org/docs/hooks-overview.html)
* [Hooks API reference](https://reactjs.org/docs/hooks-reference.html)
* [State hook docs](https://reactjs.org/docs/hooks-state.html)
* [Intro video](https://reactjs.org/docs/hooks-intro.html)