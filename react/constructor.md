# Using `props` in `constructor`

Example where `props` will be used in `constructor`:

```
class MyComponent extends React.Component {    
    constructor(props) {
        super(props)

        console.log(this.props)
        // -> { icon: 'home', … }
    }
}
```

When `props` aren't being used in the constructor, there's no need to pass them on to `super`:

```
class MyComponent extends React.Component {    
    constructor(props) {
        super()

        console.log(this.props)
        // -> undefined

        // Props parameter is still available
        console.log(props)
        // -> { icon: 'home', … }
    }

    render() {
        // No difference outside constructor
        console.log(this.props)
        // -> { icon: 'home', … }
    }
}
```

Passing or not passing `props` to `super` has no effect on later use of `this.props` outside of the `constructor`.