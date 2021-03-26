# Gatsby commands

Install the global executable: `npm install -g gatsby-cli`

list commands with `gatsby --help`

New project: `gatsby new project-name`

### run on `localhost:8000` with `gatsby develop`

### `gatsby build` or `npm run build` to start off development

`gatsby serve` - serve the production build for testing

Clean cache and public directories with `gatsby clean`

**Necessary root files:**

- `gatsby-config.js` - project metadata, plugins etc
- `gatsby-node.js` - customise Gatsby's Node.js API, extend default settings
- `gatsby-browser.js` - customise and extend default settings for the browser using Gatsby's browser API
- `gatsby-ssr.js` - server-side rendering APIs
