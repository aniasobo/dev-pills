# 😍 ES6 🤯

## Higher order functions - 🦄 Filter and Reject

```
var animals = [
  {name: 'Spot', species: 'dog'},
  {name: 'Black Dynamite', species: 'horse'},
  {name: 'Dingo', species: 'dog'}
];

var isDog = function(animal) {
  return animal.species === 'dog'
};

var dogs = animals.filter(isDog);

var otherAnimals = animals.reject(isDog);
```

## 💥 Map

```
var names = animals.map((animal) => animal.name);

// equivalent of:

var names = animals.map(function(animal){
  return animal.name
});
```

## 🤺 Arrow functions

```
const dragonEvents = [
  {type: 'attack', value: 12, target: 'horse'},
  {type: 'eat', target: 'not horse'},
  {type: 'pet', value: 3, target: 'horse'}
]

const damagaToHorse = dragonEvents
    .filter(event => event.type === 'attack')
    .filter(event => event.target === 'horse')
    .map(event => event.value)
    .reduce(prev, value => (prev || 0) + value); // outcome: sum of values
```

## 🔥 Reduce

Passing a callback function to `reduce` in the previous example:

```
const reduceTotal = (prev, x) => (prev || 0) + x;

const damagaToHorse = dragonEvents
    .filter(event => event.type === 'attack')
    .filter(event => event.target === 'horse')
    .map(event => event.value)
    .reduce(reduceTotal);
```

## 🧙🏻‍♀️ Array and string destructuring

```
// array

var user = ['Name Lastname', 'email@inbox.com', 'Location']

var [name, handle, location] = user;

// string

var csv = "1997, Ford, F350, Must Sell!"

var [year, make, model, description] = csv.split(', ');
```

---
all the above examples loosely adapted from videos by [Fun Fun Function](https://www.youtube.com/channel/UCO1cgjhGzsSYb1rsB4bFe4Q)

**more Desctructuring:** 

[5 Interesting Uses of JS Destructuring](https://dmitripavlutin.com/5-interesting-uses-javascript-destructuring/)

**more first-class functions:**

[First-Class Functions in JS](https://nick.scialli.me/first-class-functions-in-javascript/)