# Using strict mode in React

* useful for catching outdated features, debug concurrency and future-proof the code against deprecations
* points out legacy APIs
* flags unsafe lifecycle methods
* detects side effects
* only runs in development mode and doesn't affect production code
* doesn't render anything visual (like `<Fragment>`)

On the entire `<App />`:

```
<React.StrictMode>
  <App>
    <Component1 />
    <Component2 />
  </App>
</React.StrictMode>
```

On a single component:

```
<App>
  <React.StrictMode>
    <Component1 />
  </React.StrictMode>
  <Component2 />
</App>
```

[Source - React Christmas 2019](https://react.christmas/2019/1)
