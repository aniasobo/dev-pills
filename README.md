# Today I learned <!-- omit in toc -->

Following the practice of [@jbranchaud](https://github.com/jbranchaud/til), [thoughtbot](https://github.com/thoughtbot/til) and [@charliegerard](https://github.com/charliegerard/dev-notes).

A collection of my tips and tricks learnt over the course of the Makers Academy bootcamp, as well as ongoing learning.

---

# Categories <!-- omit in toc -->

- [Testing](#testing)
  - [RSpec & testing Ruby](#rspec--testing-ruby)
  - [JavaScript testing](#javascript-testing)
- [Git](#git)
- [Command line](#command-line)
- [Editors](#editors)
  - [VSCode](#vscode)
  - [Vim](#vim)
- [APIs](#apis)
- [JavaScript](#javascript)
  - [Web APIs](#web-apis)
- [Typescript](#typescript)
- [Node.js](#nodejs)
- [JavaScript frameworks and libraries](#javascript-frameworks-and-libraries)
  - [React](#react)
  - [Redux](#redux)
  - [Vue](#vue)
  - [Gatsby](#gatsby)
  - [Next.js](#nextjs)
  - [Nest.js](#nestjs)
  - [Ramda](#ramda)
- [Python](#python)
- [Ruby](#ruby)
  - [Rails](#rails)
- [`C#`](#c)
- [Elixir](#elixir)
- [Front-end](#front-end)
- [CSS](#css)
  - [CSS basics](#css-basics)
  - [`flexbox`, `grid` and other layouts](#flexbox-grid-and-other-layouts)
  - [Miscallaneous tips and tricks](#miscallaneous-tips-and-tricks)
  - [CSS resources](#css-resources)
- [Postgres](#postgres)
- [Go](#go)
- [Rust](#rust)
- [WebAssembly](#webassembly)
- [Mobile developent](#mobile-developent)
  - [Flutter & Dart](#flutter--dart)
- [Project setups](#project-setups)
- [DevOps/SRE](#devopssre)
- [Machine learning](#machine-learning)
- [Authentication](#authentication)
- [Computer science](#computer-science)
- [Electrical engineering](#electrical-engineering)
  - [Misc hardware](#misc-hardware)
  - [Raspberry Pi](#raspberry-pi)
  - [JavaScript-controlled bots](#javascript-controlled-bots)
- [Misc](#misc)
- [Tech interviews](#tech-interviews)

---

# Testing

- [Chrome dev tools](testing/chrome-dev-tools.md)
- [London vs Chicago schools of TDD](testing/schools.md)
- [Examples of testing systems](testing/examples.md)

## RSpec & testing Ruby

- [RSpec setup](testing/rspec-setup.md)
- [RSpec syntax](testing/rspec-syntax.md)
- [RSpec mocking](testing/rspec-mocks.md)
- [Pry](testing/pry.md)
- to add: Capybara
- [Rubocop scaffold](testing/rubocop.yml)
- [FactoryBot](testing/factorybot.md)
- [Factories: `build` vs `create`](testing/factory-build-create.md)
- [Factories: `let` vs `let!`](testing/factorybot-let.md)

## JavaScript testing

- [ESLint setup](testing/eslint.md)
- [Jasmine](testing/jasmine.md)

---

# Git

- [Commit messages](git/commit-messages.md)
- [Git resources](git/git-resources.md)
- [.gitignore](git/gitignore.md)
- [Git Basics](git/basics.md)
- [GitHub: find historic file](git/history.md)
- to add: working on branches

---

# Command line

- [zsh resources](command-line/zsh.md)

---

# Editors

## VSCode

- [VSCode extensions](editors/vscode-extensions.md)
- [VSCode tricks](editors/vscode-tricks.md)

## Vim

- [`vimtutor` notes](editors/vimtutor.md)
- [Vim + VSC cheatsheet](editors/vim.md)
- [Notes from Vim talks](editors/vim-talks.md)

---

# APIs

- [List of cool APIs](api/list.md)
- [Web APIs](api/web-apis.md)
- [Webhooks](devops/webhooks.md)
- [Axios](api/axios.md)
- [Remote data fetching in React](api/react-fetching.md)
- [RESTful APIs](misc/rest.md)
- [REST clients](api/clients.md)
- [GraphQL resources](api/graphql.md)

---

# JavaScript

- [JS basics and overview](javascript/js-basics.md)
- [Functional programming sample](javascript/export-functions.md)
- [Pure functions](cs/pure-functions.md)
- [JS resources](javascript/js-resources.md)
- [Logical operators in JS](javascript/logical-operators.md)
- [Prototyping and inheritance](javascript/inheritance.md)
- [OO and inheritance in JS](javascript/oo.md)
- [Module pattern & `this`](javascript/module-pattern.md)
- [Destructuring](javascript/destructuring.md)
- [ES6 functions and destructuring](javascript/es6-fun.md)
- [ES6 Rest & Spread](javascript/rest-spread.md)
- [Arrow functions](javascript/arrow.md)
- [Nested functions](javascript/nested-functions.md)
- [Fetching data with axios vs fetch()](javascript/axios-fetch.md)
- [Currying](javascript/currying.md)
- [Hoisting](javascript/hoisting.md)
- [Closures](javascript/closures.md)
- [Promises](javascript/promises.md)
- [Debugging JS](javascript/debugging.md)
- [Error handling](javascript/error-handling.md)
- [Export-import cheatsheet](javascript/exports-cheatsheet.md)
- [`const`, `let` and `var`](javascript/const-let-var.md)
- [`Set` object](javascript/set.md)
- [JS Date module](javascript/date.md)
- [JS for React](javascript/js-react.md)
- [Handy JS and TS libraries](javascript/libraries.md)

## Web APIs

- [Query selectors](javascript/query-selectors.md)
- [`window.location`](javascript/window-location.md)

---

# Typescript

- [What is TypeScript](typescript/typescript.md)
- [Typescript resources](typescript/resources.md)

---

# Node.js

- [Node middleware & resources](node/resources.md)
- [Node execution model](node/execution-model.md)
- [Event Emitters](node/event-emitters.md)

---

# JavaScript frameworks and libraries

## React

- [React resources](react/react-resources.md)
- [React intro notes](react/react-intro-notes.md)
- [Intro to testing React](react/react-intro-testing.md)
- [Strict Mode](react/strict-mode.md)
- [React Dev Tools](react/dev-tools.md)
- [React hooks](react/hooks.md)
- [Enzyme vs React Testing Library](react/testing-libraries.md)
- [`prop-types` library](react/prop-types.md)
- [Conditional rendering in component](react/conditional-rendering.md)
- [React.Fragment](react/fragments.md)
- [Using `props` in `constructor`](react/constructor.md)
- [Passing `props` with the spread operator](react/spread.md)
- [React lifecycyle methods](react/lifecycle-methods.md)
- [Functional vs class components](react/functional-components.md)
- [React Context API and hook](react/context-api.md)
- [Firing events in React](react/events.md)`
- [Promises and async-await syntax](javascript/promises.md)
- [Custom `data-` and `aria-` attributes](react/data-aria.md)
- [Libraries - cool libs to use with React](react/libraries.md)
- [Security vulnerabilities in React](react/security-vulnerabilities.md)
- [State in React](cs/state.md)
- [5 Types of React Application State](redux/state-types.md)

---

## Redux

- [Redux intro notes](redux/redux-intro-notes.md)
- [Alternatives to Redux](redux/alternatives.md)
- [Types of React Application State](redux/state-types.md)
- [State management in Redux](redux/state-management.md)
- [Action creators and `redux-thunk`](redux/action-creators.md)

---

## Vue

- [Vue resources](vue/vue-resources.md)

---

## Gatsby

- [Gatsby resources](gatsby/gatsby.resources.md)
- [Cheatsheet](gatsby/cheatsheet.md)
- [Themes](gatsby/themes.md)
- [Gatsby Cloud](gatsby/gatsby-cloud.md)

---

## Next.js

- [Next.js resources](next/resources.md)

---

## Nest.js

- [Nest.js resources](nest/resources.md)

---

## Ramda

- [Using Ramda](ramda/using-ramda.md)

---

# Python

- [Syntax: underscore](python/underscore.md)
- [Web scraping in python](python/web-scraping.md)
- [Setup best practices](setup/python.md)
- [Python resources](python/resources.md)
- [Pipenv and package dependencies solutions](python/pipenv.md)
- [Dictionaries](python/dict.md)

---

# Ruby

- [Sinatra](ruby/sinatra.md)
- [Dependency injection](ruby/dependency-injection.md)
- [Date API](ruby/date-time.md)
- [Method access control](ruby/method-access-control.md)

## Rails

- [Rails basics](rails/rails.md)
- [Rails resources](rails/resources.md)
- [`.present?` vs `.any?` vs `.exists?`](rails/present-exists-any.md)
- [`respond_to format.js` API](rails/respond-to.md)
- [Active Record - `scope`](rails/active-record-scope.md)
- [Calling things on Active Record models](rails/active-record-model-calls.md)
- [Controllers writeup](rails/controllers.md)
- [Controller - standard CRUD implementation](rails/controller_template.rb)
- [ActiveRecord Models](rails/model.md)
- [Service objects](rails/services.md)

---

# `C#`

- [Resources](c-sharp/resources.md)

---

# Elixir

- [Intro notes](elixir/elixir-intro.md)

---

# Front-end

- [General front-end resource list](misc/fe-resources.md)

---

# CSS

## CSS basics

- [Syntax](css/syntax.md)
- [Units](css/units.md)
- [Selectors](css/selectors.md)
- [The CSS Cascade](css/cascade.md)
- [CSS box model](css/css-box-model.md)
- [`border-box` vs `content-box`](css/boxes.md)
- [CSS ruleset](css/css-ruleset.md)
- [CSS font sizing](css/css-font-sizing.md)
- [CSS centering](css/css-centering.md)
- [CSS transitions](css/transitions.md)
- [Gradients](css/gradients.md)
- [CSS variables/custom properties](css/variables.md)

## `flexbox`, `grid` and other layouts

- [CSS grid resources](css/debug-grid.md)
- [SCSS - basic flexbox grid](css/scss-flexbox-grid.md)
- [Simple CSS grid example](css/simple-grid.css)
- [Nested grid example](css/nested-grid.html)
- [Flexbox](css/flexbox.md)
- [Flexbox or grid?](css/flexbox-or-grid.md)
- [Default mobile first layout](css/mobile-default-layout.md)

## Miscallaneous tips and tricks

- [`user-select-all`](css/user-select.md)
- [`calc()`](css/calc.md)

## CSS resources

- [CSS resources](css/resources.md)
- [Libraries](css/libraries.md)

---

# Postgres

- [Command line postgres](postgres/commands.md)
- [Query performance](postgres/performance.md)

---

# Go

- [Learning resources](go/learning-go.md)
- [Go best practice](go/best-practice.md)
- [Features - minimal working examples of Go](go/features.go)
- [Standard package layout](go/go-package-layout.md)
- [Go frameworks](go/frameworks.md)

---

# Rust

- [Cargo](rust/cargo.md)
- [Rustup tool](rust/rustup.md)
- [Resources](rust/rust-resources.md)

---

# WebAssembly

- [Intro to WebAssembly](webassembly/intro.md)
- [WebAssembly resources](webassembly/resources.md)
- [AssemblyScript](webassembly/intro.md)

---

# Mobile developent

## Flutter & Dart

- [Flutter resources](flutter/resources.md)

---

# Project setups

- [Sinatra project with Capybara and Rspec](setup/sinatra-capybara-rspec.md)
- [Node project with Express server](setup/node-express.md)
- [React app with Node and Express backend plus webpack](setup/react-node-express-webpack.md)
- [React sample project with Webpack, tools and hooks](setup/react-webpack.md)
- [Node project boilerplates](setup/node-boilerplate.md)
- [Full stack app in Vue and Node/Express](setup/vue-node-fullstack.md)
- [MVC app in plain JS](setup/mvc-plain-js.md)
- [Nest.js CRUD with Postgres and TypeORM](setup/nest-crud.md)
- [Node.js with PyNode](setup/node-pynode.md)
- [Vue and Rails single-page app](setup/vue-rails.md)
- [Gatsby on Now](setup/gatsby.md)
- [Python setup - best practices](setup/python.md)
- [Full-stack demo](setup/medium-demo.md)
- [Python with Vue frontend - links at the bottom](vue/vue-resources.md)
- [ML projects](setup/ml.md)
- [Static site starters](setup/static-sites.md)

---

# DevOps/SRE

- [Basics of network engineering](devops/network.md)
- [HTTP](devops/http.md)
- [Webhooks](devops/webhooks.md)
- [Servers](devops/servers.md)
- [Web performance checklist](devops/web-performance-checklist.md)
- [SQL vs NoSQL databases](devops/sql-nosql.md)
- [Master-Slave Architecture](devops/master-slave.md)
- [Event Driven Architecture](devops/event-driven.md)
- [Publisher-Subscriber Model](devops/publisher-subscriber.md)
- [Heroku](devops/heroku.md)
- [Rake](devops/rake.md)
- [CI/CD setup](devops/ci-cd.md)
- [CRC cards for db models](devops/db-modelling.md)
- [Travis](devops/travis.md)
- [Antipatterns of db use](devops/antipatterns.md)

---

# Machine learning

- add notes from ML workshop
- [Libraries](ml/libraries.md)
- [ML tutorials](ml/tutorials.md)
- [TensorFlow.js](ml/js-ml.md)
- [TensorFlow 2.0 with Keras](ml/tensorflow-keras.md)
- [3D machine learning](ml/3d.md)
- [Polish language resources](ml/polish-language-resources.md)

---

# Authentication

- [OAuth resources](authentication/oauth.md)
- [OAuth vs Auth0](authentication/oauth-auth0.md)
- [Omniauth](authentication/omniauth.md)

---

# Computer science

- [CS curriculum](cs/roadmap.md)
- [Data structures](cs/data-structures.md)
- [OOP](cs/oop.md)
- [FP](cs/fp.md)
- [PWA pattern](cs/pwa.md)
- [Algorithms](cs/algorithms.md)
- [Pure functions](cs/pure-functions.md)
- [RegEx](cs/regex.md)
- [Finite State Machine pattern](cs/finite-state-machine.md)
- [State as a concept](cs/state.md)
- [Design patterns](cs/design-patterns.md)

---

# Electrical engineering

## Misc hardware

- [Sleep hacking projects](hardware/sleep-sensor.md)

---

## Raspberry Pi

- [Hardware links](hardware/resources.md)
- [Building a WiFi-connected camera system](hardware/cameras.md)

---

## JavaScript-controlled bots

- [JS bots resources](hardware/javascript-hardware.md)

---

# Misc

- [Markdown cheatsheet](misc/markdown-cheatsheet.md)
- [Accessibility tools](misc/accessibility.md)
- [Naming good practice](misc/naming.md)
- [Documenting projects](misc/documentation.md)
- [Folder structure conventions](misc/folder-structure-conventions.md)
- [Headless CMS](misc/headless-cms.md)
- [Web Design](misc/design.md)
- [Environment fixes](misc/environment-fixes.md)
- [READMEs](misc/readmes.md)
- [RESTful APIs](misc/rest.md)
- [OSINT](misc/osint.md)
- [Get a list of browsers from npx](misc/browsers.md)
- Process: [Example Mapping](misc/example-mapping.md)
- [Serverless functions](misc/serverless-functions.md)

---

# Tech interviews

- [Preparing for interviews](tech-interviews/interview-prep.md)
- [Tech interview questions](tech-interviews/questions.md)
- [Systems design concepts](tech-interviews/systems-design-concepts.md)
- [Tech test checklist](tech-interviews/tech-test-checklist.md)
- [Tech test tips](tech-interviews/tech-test-tips.md)
- [Negotiating strategy](tech-interviews/negotiating.md)
- [How to remove duplicate values from an array?](tech-interviews/remove-duplicates-from-array.md)
- [Kate's interview form](tech-interviews/interview-form.md)
- [Advanced software architecture interviews](tech-interviews/scaling-systems.md)
- [Researching the employers](tech-interviews/research.md)
