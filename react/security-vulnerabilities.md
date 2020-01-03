# Vulnerabilities in React

**XSS - cross-site scripting**
    
### Server-side rendering

Injection with initial state rendering: `<script>window.__STATE__ = ${JSON.stringify({ data })}</script>` - the `JSON.stringify()` will blindly render any data, as long as it's a string.

Common pattern when server-side rendering React with Redux.

Example of this pattern:

```
function renderFullPage(html, preloadedState) {
  return
    <!doctype html>
      <html>
        <head>
          <title>Example</title>
        </head>
        <body>
          <div id="root">${html}</div>
          <script>
            window.__PRELOADED_STATE__ = ${JSON.stringify(preloadedState)}
          </script>
          <script src="static/bundle.js"></script>
        </body>
      </html>
}
```

Use the `serialize-javascript` node module for a fix.

### Links with the `javascript:` tag - XSS vulnerability

If a page sets links based on user input, these can be attacked by injecting the tag into that input:

```
data:text/html, <a href="javascript: alert('hello from javascript!')" >click me</a>
```

Expected to be automatically escaped in future versions of React


[Source](https://medium.com/javascript-in-plain-english/3-security-pitfalls-every-react-developer-should-know-c04715b876b5)


### Setting html dangerously

[Common vulnerability when processing Markdown](https://flexport.engineering/six-vulnerabilities-from-a-year-of-hackerone-808d8bfa0014#778b)

> **The fix:**
> Wrap all text passed in to dangerouslySetInnerHtml with an XSS filter and create a Lint rule to enforce this in the future.
