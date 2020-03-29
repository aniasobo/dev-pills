# Dart notes from Eric Windmill _Flutter in Action_

- strongly typed language:
  - every variable should have a type
  - every function should return a type or `void`
  - all statements end with a `;` semicolon

## `main`

Every dart program must contain a `main` function for the Dart compiler to find:

```
void main() {
  print('Hello World!');
}
```

- `void` is the return **type** of the function
- `void` means the function won't return anything
- `print` is a function that always prints to console

## Functions

- Must have return type declared
- expression surrounded by `{}`
- statements end with `;`

## Data structures

- `List` (array)
- `String` - surrounded by single quotes?
- `int`

## String interpolation

`print('Hello, $name');`

Also done with `${}`

## `for` loops

```
for (var myVar in myList) {
  myFunction(myVar);
}
```

## Lists

```
List<String> listName = ['one', 'two',];
```

## Libraries

- `dart:core` is loaded by default
