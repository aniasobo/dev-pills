# Notes from intro to React tutorial 

* Classes in ES6 can represent components in a web application
* Classes can inherit from other classes to inherit properties and methods. Notably, React components extends the base Component class from the ‘react’ library
* **ES6 Template Strings**: Template strings provide a convenient and syntactically concise way of concatenating strings together. They use backticks and the dollar-sign curly brace syntax - `${}`, for interpolation
* ES6 imports and exports provide a convenient way to share code between files through default and regular exports
* Arrow functions in ES6 provide a syntactic alternative to functions declared with the `function` keyword. They don’t create their own `this` object which allows React components to use their own `this` object within component methods
* **Destructuring** objects in es6 gives a convenient way to declare variables whose name match key names within objects
* Components in React extends the base Component class from the ‘react’ library. They include a render function which defines their structure through JSX
* **JSX** adds XML-like syntax to JavaScript, and is the primary way to define component structure in React
* **Props**: The concept of props (properties) in React components refers to data received from parent components
* **Lifecycle hooks** including `componentDidMount` refer to methods that fire throughout specific times in the life of a React component