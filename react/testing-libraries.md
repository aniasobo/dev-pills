# React testing libraries: Enzyme vs React Testing Library

[React Testing Library docs](https://testing-library.com/docs/react-testing-library/intro)

> what Testing Library does is renders the actual HTML — so you’re testing what your user sees, rather than component instances, so your tests become much more meaningful

Guiding principle: 

> The more your tests resemble the way your software is used, the more confidence they can give you.

Rather than dealing with instances of rendered React components, your tests will work with actual DOM nodes. The utilities this library provides facilitate querying the DOM in the same way the user would. 

It's a lightweight alternative to Enzyme, though not itself a framework.

Built on top of DOM Testing Library.

Encourages building accessible components becase the tests don't target them by css selectors.

## Differences to Enzyme

[Shallow rendering](https://kentcdodds.com/blog/why-i-never-use-shallow-rendering) in Enzyme encourages testing implementation details - selecting elements by component constructors, testing state and props. 

Mounting should only be used to test that components are working as a unit.

The guiding principle of the React Testing Library prevents default testing of internals (though it is possible) and instead testing components as the user would see them.

Targets items by `data-testid` 

### Resources

* [RTL cheatsheet](https://testing-library.com/docs/react-testing-library/cheatsheet)
* [Article comparing Enzyme, Testing Library and Cypress](https://medium.com/javascript-in-plain-english/i-tested-a-react-app-with-jest-testing-library-and-cypress-here-are-the-differences-3192eae03850)
* [Rewrite Enzyme component tests in React Testing Library](https://medium.com/flatiron-labs/refactoring-an-enzyme-component-test-to-use-react-testing-library-f5c36da6716f)
* [Intro from its author, with examples](https://kentcdodds.com/blog/introducing-the-react-testing-library)
* [Moving from Enzyme to RTL](https://medium.com/@boyney123/my-experience-moving-from-enzyme-to-react-testing-library-5ac65d992ce)
* [Project with Enzyme and RTL tests](https://claritydev.net/blog/testing-react-components-enzyme-vs-react-testing-l)