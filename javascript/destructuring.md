# Destructuring in JS

Code examples from [this article on destructuring assignment](https://www.smashingmagazine.com/2019/09/reintroduction-destructuring-assignment/)

```
const response = {
   status: 200,
   data: {}
}

// instead of response.data we get...
const {data} = response //now data references the data object directly

const objectList = [ { key: 'value' }, { key: 'value' }, { key: 'value' } ]

// instead of objectList[0], objectList[1], etc we get...
const [obj, obj1, obj2] = objectList // now each object can be referenced directly
```

**Nested destructuring**  

Example object response from an HTTP request:

```
const response = {
  status: 200,
  data: { 
    user: {
       name: 'cat', 
      title: 'CEO' 
    }, 
    account: {},
    company: 'Doghouse' 
  }
}

const {data: {user}} = response // user is { name: 'cat', title: 'CEO'}
```

[5 Interesting Uses of JS Destructuring](https://dmitripavlutin.com/5-interesting-uses-javascript-destructuring/)

## Array and string destructuring from Fun Fun Function

```
// array

var user = ['Name Lastname', 'email@inbox.com', 'Location']

var [name, handle, location] = user;

// string

var csv = "1997, Ford, F350, Must Sell!"

var [year, make, model, description] = csv.split(', ');
```

