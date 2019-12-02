# `data-` and `aria-` attributes

Used for adding custom attributes in React. The only custom attributes that can be freely passed in to components are:

```
<div data-foo="42" />
<button aria-label="Close" onClick={onClose} />
```

React checks that `aria-` props have correct names in development mode.

Unknown attributes trigger a warning.
