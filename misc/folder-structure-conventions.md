# Project directory structure conventions

```
project
│   README.md
│   .env
│   .gitignore
│   demo.png
│   package.json
│   yarn.lock
└───public
│   │   index.html
│   │   logo.png
│   │   manifest.json
│   │   robots.txt
│   │   ifUsingStylesheet.css
└───src
│   │  App.js
│   │  index.js
│   │  ServiceWorker.js
│   └───tests
│   │      App.spec.js  
│   └───components
│   │      Component.js  
│   └───constants
│   │      index.js  
│   └───containers
│   │      ItemsContainer.js  
│   └───fixtures
│   │      index.js  
│   └───hooks
│   │      UseThisEffect.js  
│   └───mappers
│   │      mapTime.js  
│   └───selectors
│   │      selectFields.js  
│   └───services
│   │      thisAPI.js  
│   └───styles
│   │      StyledComponentWrapper.js  
│   └───utils
│   │      debounce.js  
```

---

# Node.js REST API service folder structure

```
src
│   app.js          # App entry point
└───api             # Express route controllers for all the endpoints of the app
└───config          # Environment variables and configuration related stuff
└───jobs            # Jobs definitions for agenda.js
└───loaders         # Split the startup process into modules
└───models          # Database models
└───services        # All the business logic is here
└───subscribers     # Event handlers for async task
└───types           # Type declaration files (d.ts) for Typescript
```

[Source](https://softwareontheroad.com/ideal-nodejs-project-structure/#folder)

---

## Rails

[Use the convention](../ruby/rails.md)
