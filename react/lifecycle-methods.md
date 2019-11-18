# Using React lifecycle methods <!-- omit in toc -->

INDEX:

- [`componentWillMount()`](#componentwillmount)
- [`componentDidMount()`](#componentdidmount)
- [`componentWillReceiveProps()`](#componentwillreceiveprops)
- [`shouldComponentUpdate()`](#shouldcomponentupdate)
- [`componentWillUpdate()`](#componentwillupdate)
- [`componentDidUpdate()`](#componentdidupdate)
- [`componentWillUnmount()`](#componentwillunmount)
- [`compontentDidCatch()`](#compontentdidcatch)

---

## `componentWillMount()`

* called right before the `render` method is called or the component mounts
* sits between the `constructor` method and the `render` method
* should NOT be used for API calls for client-side rendering, which are asynchronous so they can't be blocking the `render`
* good for performing setup that should be done at runtime
* can be used for external API calls like Firebase

## `componentDidMount()`

* available after the component has mounted
* called once in the component lifecycle
* anything that should be set up in the DOM should be set up here
* the best place for API calls that render data on the client
* good for connecting the application to other APIs or frameworks
* good for setting times with `setTimeout` and `setInterval`
* good place for event listeners
* can be used to draw on a just-rendered element
  
```
class Example extends React.Component {
        componentDidMount() {
            fetch(url).then(results => {
                // Do something with the results
            })
        }
    }
```

## `componentWillReceiveProps()`

* deprecated over 16.3?
* called before the component does anything with the new `props`, usually passed down by a parent component
* called with the new `props` passed as an argument
* both previous and updated `props` can be accessed in this method - use comparison, as it will be redundant if there's no change to `props`

## `shouldComponentUpdate()`

* called before the component re-renders after receiving new `props` or a new state
* should receive two arguments: the new `props` and the new state
* used to let React know that a component's output is not affected by a change in `props` or state and so should not re-render
* returns either `true` or `false`
* if it returns `true`, the component will re-render; it will not update if `false` - this does not prevent child components from re-rendering when their state changes though
* used correctly should return `false` to specify the conditions under which the component should not update
* good place to focus on to improve performance because it will stop needless re-rendering

## `componentWillUpdate()`

* deprecated over 16.3?
* used to perform preparation for re-rendering
* cannot call `this.setState` in this method
* used for interacting with things outside of React architecture and non-React setup such as API calls, checking window size etc
* paired with `shouldComponentUpdate()` to tell it how to re-render on prop/state change
* should not be used for animations because it might be called multiple times before the component is actually re-rendered

## `componentDidUpdate()`

* called after any rendered html has finished loading
* takes two arguments, `props` and state of the component before the current update
* best place to interact with non-React environment such as the browser, http requests - but only when you compare previous `props` to new `props` to avoid unnecessary network requests

## `componentWillUnmount()`

* called right before a component is removed from DOM
* perform cleanups here - invalidating timers, cancelling network requests, removing event listeners, cancelling subscriptions made in `componentDidMount()`

## `compontentDidCatch()`

* used in a component to make it an error boundary
* `this.setState` can be called here and used to catch unhandled erros in child components to display fallback UI instead of a crashed component
* ensures that a break in a child component won't crash the whole app
* does not catch errors in the component itself - only its children
* takes two paramenters: the error and an object with a `componentStack` property containing the stack trace info
* the parameters allow you to set the error info in state and return an appropriate message in the `render` method

[Source](https://blog.pusher.com/beginners-guide-react-component-lifecycle/)