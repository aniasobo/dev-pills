# Dart notes from Eric Windmill _Flutter in Action_

- strongly typed language:
  - every variable should have a type
  - every function should return a type or `void`
  - all statements end with a `;` semicolon
  - typing is done at compile-time
- object-oriented
- supports single inheritance
- everything is an object and inherits from the Object class - that includes numbers; there are no primitives in Dart
- support for top-level functions and variables, often called _library members_
- Dart is _lexically_ scoped

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

---

# Dart intro

## Type system

- type is inferred, so if it's not explicitly assigned but given a return value, the value will be assigned as the type by the compiler: `var name = 'Anna';` cannot be reassigned to an int, it will always have to be a string instance
- the type always comes before the value it describes:

```
String name;
int age;

int greeting = 'Hello'; // this will not compile
```

- for complex data structures like `List` or `Map`, define the type within in a pair of `<>`:

```
List<String> names;       // list of strings
List<int> ages;           // list of ints
Map<String, int> people;  // map whose keys are strings and values are ints
```

- for functions that return something other than nothing/`void`:

```
int addNums() {
  // returns an int
}

int addNums(int x, int y) {     // args also have specified types
  return x + y
}
```

- option to set a `dynamic` type i.e. allow the compiler to accept any type in given var or func:

```
dynamic myNum = 'Hello'; // this could be anything
```

- dynamic typing is mostly used for Maps, for example when working on JSONs: `Map<String, dynamic> json;`

## Comments

```
// inline comment

/// use this to document your classes
///
/// like this

/*
block comments work but
it's against Dart convention to use them
*/
```

## `null`

- `null` is an object
- any type var can be assinged to `null`
- unassigned but instantiated objects point to `null` by default

## `final`, `const` and `static`
