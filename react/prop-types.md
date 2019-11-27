# React `prop-types`

Typechecking library for React props.

Assign the special `propTypes` property to your component to run typechecking on its props:

```
import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};
```

[Docs](https://reactjs.org/docs/typechecking-with-proptypes.html)

`PropTypes.shape()` can be used to validate all attributes from an object; it needs to receive and object with all attributes as param, like so:

```
import React from 'react'
import PropTypes from 'prop-types'

const User = ({ user }) =>
  <div>
    My name is: {user.name}
    I am {user.age} years old
  </div>

User.propTypes = {
  user: PropTypes.shape({
    name: PropTypes.string.isRequired,
    age: PropTypes.number.isRequired
  })
}

export default User
```