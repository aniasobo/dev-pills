# Conditional rendering in a React component

## Creating functions that render elements and calling them with standard `if-else` statement

* Use handler functions that get called if a prop points one way
  
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
