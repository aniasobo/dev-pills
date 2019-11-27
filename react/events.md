# Adding events to React components

## `onClick()`

Always use the anonymous function syntax: `onClick={() => functionToFire(prop)}`; using just function name without `() => {}` uses the return value of the function instead of execting the function itself - so the function gets executed when the component renders, which might mess up with state etc