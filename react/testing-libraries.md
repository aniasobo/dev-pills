# React testing libraries: Enzyme vs React Testing Library

[React Testing Library docs](https://testing-library.com/docs/react-testing-library/intro)

> what Testing Library does is renders the actual HTML — so you’re testing what your user sees, rather than component instances, so your tests become much more meaningful

Guiding principle: 

> The more your tests resemble the way your software is used, the more confidence they can give you.

Rather than dealing with instances of rendered React components, your tests will work with actual DOM nodes. The utilities this library provides facilitate querying the DOM in the same way the user would. 

It's a lightweight alternative to Enzyme, though not itself a framework.

Built on top of DOM Testing Library.

## Differences to Enzyme

Shallow rendering in Enzyme encourages testing implementation details - selecting elements by component constructors. 

The guiding principle of the React Testing Library prevents default testing of internals (though it is possible) and instead testing components as the user would see them.