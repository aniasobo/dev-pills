# Dart notes from Eric Windmill _Flutter in Action_ <!-- omit in toc -->

- [Basics](#basics)
- [`main`](#main)
- [Functions](#functions)
- [Data structures](#data-structures)
- [String interpolation](#string-interpolation)
- [Lists](#lists)
- [Libraries](#libraries)
- [Type system](#type-system)
- [Comments](#comments)
- [`null`](#null)
- [`final`, `const` and `static`](#final-const-and-static)
- [Operators](#operators)
- [Null-aware operators](#null-aware-operators)
  - [`?.`](#)
  - [`??`](#-1)
  - [`??=`](#-2)
- [Control flow](#control-flow)
  - [`if` and `else`](#if-and-else)
  - [`switch` and `case`](#switch-and-case)
  - [Loops](#loops)
- [Classes](#classes)
  - [Constructors](#constructors)
  - [Inheritance](#inheritance)
  - [factories and named constructors](#factories-and-named-constructors)
  - [Enumerators](#enumerators)

---

## Basics

- strongly typed language:
  - every variable should have a type
  - every function should return a type or `void`
  - all statements end with a `;` semicolon
  - typing is done at compile-time
- object-oriented
- supports single inheritance
- everything is an object and inherits from the Object class - that includes numbers; there are no primitives in Dart
- support for top-level functions and variables, often called _library members_
- Dart is _lexically_ scoped - each code block has access to the variables "above" it

---

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

---

## Functions

- Must have return type declared
- expression surrounded by `{}`
- statements end with `;`

Basic function:

```
void main() {

}
```

- function signature follows this pattern: `ReturnType functionName(ArgumentType arg)`
- function with only one expression can be written as a single-line arrow function: `String makeGreeting(String name) => 'Hello, $name';`
- parameters:
  - positional parameters (optional, denoted by being inside a pair of `[]`)
  - named parameters (optional by default unless `@required`)
  - optional positional and named parameters
  - combination of the above
  - default parameter value denoted by `=`

```
// two named parameters in a function call:
debugger(message: 'A bug!', lineNum: 44);

// named parameters in a function declaration:
void debugger({String message, int lineNum}) {
  // bla
}

// non-optional named parameters:
Widget build({@required Widget child}) { // use a Dart library called meta to use @required
  // bla
}

// default value of 5
addSomeNums(int x, int y, [int z = 5]) => x + y + z;
```

- Dart supports higher-order functions (functions that take functions as parameters and/or return functions)

---

## Data structures

- `List` (array)
- `String` - surrounded by single quotes?
- `int`

---

## String interpolation

`print('Hello, $name');`

Also done with `${}`

---

## Lists

```
List<String> listName = ['one', 'two',];
```

---

## Libraries

- `dart:core` is loaded by default

---

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

---

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

---

## `null`

- `null` is an object
- any type var can be assinged to `null`
- unassigned but instantiated objects point to `null` by default

---

## `final`, `const` and `static`

- keywords for variable types
- `final` and `const` are immutable
- `final` variables can be declared before they're set at the class level - usually in the constructor
- `const` variables won't be declared before they're assigned, but they're always the same/immutable at compile time

```
// acceptable:

const String name = 'Anna';

// not acceptable, because value could change at compile time:

const String name = 'Anna $lastname';
```

- `const` use is encouraged due to performance benefits
- `static` modifier is used only in classes

---

## Operators

| Description              | Operators                                                            |
| ------------------------ | -------------------------------------------------------------------- |
| Arithmetic               | `*` `/` `%` `~/` `+` `-`                                             |
| Relational and type test | `>=` `>` `<=` `<` `as` `is` `is!`                                    |
| Equality                 | `==` `!=`                                                            |
| Logical and/or           | `&&` `||`                                                            |
| Assignment               | `=` `*=` `/=` `~/=` `%=` `+=` `-=` `<<=` `>>=` `&=` `^=` `|=` `??=`  |
| Unary                    | `expr++` `expr--` `.` `?.` `-expr` `!expr` `~expr` `++expr` `--expr` |

- `~/` integer division operator; never returns a decimal, but rounds up to the nearest int
- `as` is a keyword that typecasts
- `is` and `is!` check that objects are the same type; equivalent to `==` and `!=`
- the keyword `expr` can be ignored - only for readability purposes

---

## Null-aware operators

- operators that bypass `null` values without throwing errors
- `?.`, `??` and `??=`

### `?.`

- assign to `null` without throwing an error
- will be an error to call on `null` without this operator

```diff
  void getUserAge(String username) async {
    final request = UserRequest(username);
    final response = await request.get();
    User user = new User.fromResponse(response);
-   if (user != null) {
-     this.userAge = user.age;
-   }
+   this.userAge = user?.age;
  // etc
}
```

### `??`

- assign fallback/default value
- use the fallback value if `null`

```
void getUserAge(String username) async {
  final request = new UserRequest(username);
  final response = request.get();
  User user = new User.fromResponse(response);
  this.userAge = user.age ?? 18; // if user age is null, fall back to 18
// etc
}
```

### `??=`

- assign this value if the object is `null`
- if not `null`, return the object as is
- makes code more concise

```
int x = 5;

// will not be reassinged because x already has value
x ??= 3;
```

---

## Control flow

### `if` and `else`

- Dart supports `if`, `else if` and `else`
- use `&&` and `||` for conditions
- explicit `true` and `false`

### `switch` and `case`

- `switch` for many conditions for the same value
- compare `int`s and `String`s with `==`
- compare values of the same type
- always end `case` with explicit `break` or `return` statement
- omit explicit `break` to go through many cases in order
- `return` immediately ends the execution and breaks out of the `switch` statement
- `throw` will throw an error and exit
- `continue` with a label - additional logic:

```
String animal = 'tiger';

switch(animal) {
  case 'tiger:
    print('its a tiger');
    continue alsoCat;
  case 'lion':
    print('its a lion');
    continue alsoCat;
  alsoCat:
  case 'cat':
    print('its a cat');
    break;
    // the string 'its a cat' will be printed out with each case
}
```

### Loops

```
for (var myVar in myList) {
  myFunction(myVar);
}
```

- `for`
- `for-in`
- `while`
- `do while`
- `forEach`:
  - method for iterables, like Lists
  - creates new scope
  - cannot use return values
  - best for modifying objects
  - is a higher-order function

```
List<String> animals = ['dog', 'cat', 'monkey'];

animals.forEach((animal) => animal.makeSound());
```

- loops in Dart use the `break` and `continue` keywords

---

## Classes

- use the `class` keyword to define a new class
- keyword `new` is inferred and therefore redundant - it's also a bad practice to use it

```diff
class Cat {
  String name;
  String color;
}

// instance of Cat:
- Cat nora = new Cat();
+ Cat nora = Cat();

nora.name = 'Nora';
nora.color = 'tabby';
```

### Constructors

```
  class Animal {
-    String name;
-    String type;
+    String name, type;

// default constructor
-    Animal(String name, String type) {
-      this.name = name;
-      this.type = type;
-    }
+   Animal(this.name, this.type);
  }
```

### Inheritance

- `class Cat extends Mammal {}`
- superclass plus new functionality == class inheritance

### factories and named constructors

### Enumerators
