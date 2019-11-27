# Fragments

Groups a list of children without adding extra nodes to the DOM. 

Solves the problem  of component with children having to be returned as a `<div>` due to the requirement of only returning one element.

## Syntax:

Long syntax:

```
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}
```

Regular syntax (requires `import React, { Fragment } from 'react'`):

```
render() {
  return (
    <Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </Fragment>
  );
}
```

Short syntax (babel 7 or higher):

```
render() {
  return (
    <>
      <ChildA />
      <ChildB />
      <ChildC />
    </>
  );
}
```

Problem solved:

```
class Columns extends React.Component {
  render() {
    return (
      <div>
        <td>Hello</td>
        <td>World</td>
      </div>
    );
  }
}
```

In the above example, the columns could not be returned on their own without a wrapping element, but wrapping them in a `div` would break the table in which they're to be rendered.