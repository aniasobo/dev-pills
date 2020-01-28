# Action creators in Redux and `redux-thunk`

Action creators - functions that return `action` objects.

Example action creator:

```
function addToCart(product) {
  return {
    type: "ADD_TO_CART",
    payload: product
  };
}
```

**Dispatching** an action asynchronously (for example, after we perform a `fetch` to save or load data from an API) - using [`redux-thunk`](https://github.com/reduxjs/redux-thunk), a Redux middleware that allows us to return thunks from action creators.

```
function loadProducts() {
  // Return a thunk
  return function(dispatch) {
    fetch("some-product-api-url")
      .then(res => res.json())
      .then(data => {
        dispatch({
          type: "ADD_PRODUCTS",
          payload: data.products
        });
      });
  };
}
```
