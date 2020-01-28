# State as a concept

State = data over time

In an app like React or Vue (or any other app), state is the status of the app - for example, user logged in.

Managing state - turning state into a **data structure** where we can read from state (get values of data) and set the state (write into those values). The data structure is often an object (for example the common `this.state = {};`).

Updating state - best practice says to do so **immutably** - that means copying the previous state before updating it to make sure the new state doesn't reference any old and incorrect values. Since state updates usually depend on the previous state, making them immutable makes sense. Good practice in React: shallow clone the state object with the [spread](../javascript/rest-spread.md) operator, only update the values that are being altered.

Reading from state - in JS, use [destructuring](../javascript/destructuring.md) to get the values you want, like so: `const { isAuth, error } = this.state;`

[SOURCE - React in 2020](https://dev.to/codeartistryio/what-is-state-and-why-should-we-care-about-it-4o95)
