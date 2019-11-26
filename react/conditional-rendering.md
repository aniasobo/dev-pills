# Conditional rendering in a React component

## Creating functions that render elements and calling them with standard `if-else` statement

* Use handler functions that get called if a prop points one way
* use `null` to prevent `render` - though this doens't affect the component lifecycle
* 
  
## Inline `if` with logical `&&` operator 

```
function Mailbox(props) {
  const unreadMessages = props.unreadMessages;
  return (
    <div>
      <h1>Hello!</h1>                                // always rendered
      {unreadMessages.length > 0 &&                  // only rendered if true
        <h2>
          You have {unreadMessages.length} unread messages.
        </h2>
      }
    </div>
  );
}

const messages = ['React', 'Re: React', 'Re:Re: React'];
ReactDOM.render(
  <Mailbox unreadMessages={messages} />,
  document.getElementById('root')
);
```

Another example:

```
!view && (
  <p>
    <input
      onChange={this.handleChange}
      value={this.state.inputText} />
  </p>
)

// as opposed to the bad:

{
  view
  ? null
  : (
    <p>
      <input
        onChange={this.handleChange}
        value={this.state.inputText} />
    </p>
  )
}
```

[Source](https://blog.logrocket.com/conditional-rendering-in-react-c6b0e5af381e/)

* Embed expression in JSX by wrapping it in `{}`
* Works based on the fact that in JS, `true && expression` always evaluates to `expression` and `false && expression` always evaluates to `false`
* [CodePen for the above](https://codepen.io/gaearon/pen/ozJddz?editors=0010)


Inline:

```
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      The user is <b>{isLoggedIn ? 'currently' : 'not'}</b> logged in.
    </div>
  );
}
```

Larger conditional expression:

```
render() {
  const isLoggedIn = this.state.isLoggedIn;
  return (
    <div>
      {isLoggedIn ? (
        <LogoutButton onClick={this.handleLogoutClick} />
      ) : (
        <LoginButton onClick={this.handleLoginClick} />
      )}
    </div>
  );
}
```

Conditional rendering using an IIFE:

```
{
  (() => {
    const handler = view 
                ? this.handleEdit 
                : this.handleSave;
    const label = view ? 'Edit' : 'Save';
          
    return (
      <button onClick={handler}>
        {label}
      </button>
    );
  })()
}
```

## Preventing component from rendering by returning `null` instead of its render output

This component will not render if the value of the prop is `false`:

```
function WarningBanner(props) {
  if (!props.warn) {
    return null;
  }

  return (
    <div className="warning">
      Warning!
    </div>
  );
}

class Page extends React.Component {
  constructor(props) {
    super(props);
    this.state = {showWarning: true};
    this.handleToggleClick = this.handleToggleClick.bind(this);  // must bind this to use it to set state later
  }

  handleToggleClick() {
    this.setState(state => ({
      showWarning: !state.showWarning  // does this just toggle?
    }));
  }

  render() {
    return (
      <div>
        <WarningBanner warn={this.state.showWarning} />
        <button onClick={this.handleToggleClick}>
          {this.state.showWarning ? 'Hide' : 'Show'}
        </button>
      </div>
    );
  }
}

ReactDOM.render(
  <Page />,
  document.getElementById('root')
);
```

## Common antipatterns

* if a random 0 appears, it might be because 0 is returned as a string and not a falsy value in React. to guard against this, use `!!varName` for the variable assigned 0 to force it into a boolean (this commonly happens when `&&` operator is used and the left-hand value ends up a 0)
* handling nulls?