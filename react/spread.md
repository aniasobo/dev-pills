# Using the spread operator to pass down props

```
function App() {
  const name = {
    first: "Reed",
    last: "Barger"
  };

  return (
    <div>
      {/*    
     <UserGreeting 
       first={name.first}
       last={name.last}
      />
      */}
      <UserGreeting {...name} />
    </div>
  );
}

function User({ first, last }) {
  return (
    <p>
      Hi, {first} {last}
    </p>
  );
}
```

[SOURCE](https://dev.to/codeartistryio/10-javascript-concepts-you-need-to-master-react-cheatsheet-3njh)
