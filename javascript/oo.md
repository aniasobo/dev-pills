# Object-orientation in JS

Object-object relationship instead of object-class relationship. (reference to object which is the prototype).

Instance-like objects are created with the keyword `new`, like so: `var cat = new Cat();`

## Constructor objects can be created in the following ways:

**1. Using the same creator function, with each instance being an independent object:**  

```
var makeCat = function() {
  var newCat = {}
  newCat.meow = function() {
    console.log("Meow");
  };
  return newCat;
};

// instantiation
var tabbyCat = makeCat();
var calicoCat = makeCat();
```

* never change their behavior
* independent from each other and the blueprint object
* poor performance - memory allocation to each thus created function

**2. Using a constructor function:**  

* function starting with capital letter indicates constructor function (convention)

```
var Cat = function() {
  this.meow = function() {
    console.log("meow");
  };
};

// instantiation

var myCat = new Cat();
```

* the `new` keyword is what creates the instance object; the `this` keyword is the hinge by which the `meow` function is attached (implicit `return this;` at the end of the constructor function; instance is attached to constructor the way of a passed argument)
* `console.log(myCat.constructor)` will output `[Function: Cat]`
* all instances of the `Cat` function are linked to the constructor

**3. Using prototyping:**  

* create object with no properties, then add functions via its prototype

```
var Cat = function() {};

Cat.prototype.meow = function() {
  console.log("meow");
};

// instantiation

var tabbyCat = new Cat();

tabbyCat.meow(); // executes Cat.prototype.meow() and outputs "meow"
```

* all cats' behaviour can be changed after they were created by altering the prototype object, because JS objects are changed at runtime - that means that if the prototype gets edited even further down in the same script, calling the altered functions on the instances will have same effect
* prototype's functions can be overridden on a per-object basis
* (in classic OO languages, the object behaviour cannot be altered at runtime)
* a lot more memory efficient than previous solution, due to the runtime creation of the prototype's instances
       
**4. Using `Object.create()`:**  

Basic implementation:  

```
Object.create = function(x) {
  var Y = function() {};
  Y.prototype = x;
  return new Y();
};
```

Example:

```
var cat = {};

cat.meow = function() {
  console.log("meow");
};

var animal = Object.create(cat);
animal.yawn = function() {
  console.log("yawn!");
};

var tabbyCat = Object.create(animal);

tabbyCat.meow(); // outputs "meow"
tabbyCat.yawn(); // outputs "yawn!"
```

* not great memory efficiency

     
## Inheritance in JS

* runs through a chain of prototypes to find where the function is defined

```
var Animal = function() {};

Animal.prototype.yawn = function() {
  console.log("yawn!");
};

var Cat = function() {};

Cat.prototype = new Animal();
Cat.prototype.meow = function() {
  console.log("meow");
};

var tabbyCat = new Cat();

tabbyCat.yawn(); // outputs "yawn!"
tabbyCat.meow(); // outputs "meow"
```

    
         
Source: Manuel Kiessling's [Node Craftsman](https://leanpub.com/nodecraftsman) book

---

# OO in ES6 syntax

for classic MVC:

```
class Model {
  constructor() {}
}

class View {
  constructor() {}
}

class Controller {
  constructor(model, view) {
    this.model = model;
    this.view = view;
  }
}

const app = new Controller(new Model(), new View());
```

Initializing a constructor function:

```
function Hero(name, level) {
  this.name = name
  this.level = level
}
```

## Defining methods

**In ES6 notation**

```
class Hero {
  constructor(name, level) {
    this.name = name
    this.level = level
  }

  // Adding a method to the constructor
  greet() {
    return `${this.name} says hello.`
  }
}
```

**non-ES6**

By assigning them directly to the prototype:

```
function Hero(name, level) {
  this.name = name
  this.level = level
}

// Adding a method to the constructor
Hero.prototype.greet = function() {
  return `${this.name} says hello.`
}
```

## Extending a class

In this example, Mage is a more specific instance of Hero, and inherits its properties and methods.

**In ES6 notation**

Using the `super` keyword + `extends`:

```
// Creating a new class from the parent
class Mage extends Hero {
  constructor(name, level, spell) {
    // Chain constructor with super instead of call()
    super(name, level)

    // Add a new property
    this.spell = spell
  }
}
```
**non-ES6**

Using the `call()` method:

```
// Creating a new constructor from the parent
function Mage(name, level, spell) {
  // Chain constructor with call
  Hero.call(this, name, level)

  this.spell = spell
}

// Creating a new object using Hero's prototype as the prototype for the newly created object.
Mage.prototype = Object.create(Hero.prototype)
```

Both are instantiated using the `new` keyword.

Source: [Tania Rascia](https://www.taniarascia.com/understanding-classes-in-javascript/)