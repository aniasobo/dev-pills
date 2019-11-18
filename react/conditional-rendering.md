# Conditional rendering in a React component

## Creating functions that render elements and calling them with standard `if-else` statement

* Use handler functions that get called if a prop points one way
  
## Inline `if` with logical `&&` operator

```
function Mailbox(props) {
  const unreadMessages = props.unreadMessages;
  return (
    <div>
      <h1>Hello!</h1>
      {unreadMessages.length > 0 &&
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