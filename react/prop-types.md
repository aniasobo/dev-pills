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