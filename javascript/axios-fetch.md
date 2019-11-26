# Axios vs `fetch()` for data fetching

axios uses the `data` property while `fetch()` uses the `body` property:

### Axios:

```
const options = {
  url: 'http://localhost/test.htm',
  method: 'POST',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json;charset=UTF-8'
  },
  data: {
    a: 10,
    b: 20
  }
};

axios(options)
  .then(response => {
    console.log(response.status);
  });
```

### `fetch()`:

```
const url = 'http://localhost/test.htm';
const options = {
  method: 'POST',
  headers: {
    'Accept': 'application/json',
    'Content-Type': 'application/json;charset=UTF-8'
  },
  body: JSON.stringify({
    a: 10,
    b: 20
  })
};

fetch(url, options)
  .then(response => {
    console.log(response.status);
  });
```

* the data in `fetch()` is stringified
* url is passed as argument to `fetch()` but set in the options object for `axios`

**Advantages of `axios`:**

* wider browser support
* no need to use polyfills for data fetching
* simplicity of setting timeout (optional `timeout` property in the config object)
* automatically stringyfies data
* can intercept HTTP requests
* easy implementation of a progress indicator
* ease of making multiple requests with an array of requests passed into `axios.all()`, then with `axios.spread()`:

```
axios.all([
  axios.get('https://api.github.com/users/iliakan'), 
  axios.get('https://api.github.com/users/taylorotwell')
])
.then(axios.spread((obj1, obj2) => {
  // Both requests are now complete
  console.log(obj1.data.login + ' has ' + obj1.data.public_repos + ' public repos on GitHub');
  console.log(obj2.data.login + ' has ' + obj2.data.public_repos + ' public repos on GitHub');
}));
```

[SOURCE](https://blog.logrocket.com/axios-or-fetch-api/)