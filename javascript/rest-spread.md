# Rest and Spread

![rest and spread code](rest-spread.png)  

credit: [@colepeters](https://github.com/colepeters)

# Common use cases

**1. Copying an array**

```
const fruits = ['apple', 'orange', 'banana'];
const fruitsCopied = [...fruits]; // ['apple', 'orange', 'banana']

console.log(fruits === fruitsCopied); // false
```

**2. Remove duplicates from array**

```
const fruits = ['apple', 'orange', 'banana', 'banana'];
const uniqueFruits = [...new Set(fruits)]; // ['apple', 'orange', 'banana']
```

**3. Concatentate arrays**

```
const fruits = ['apple', 'orange', 'banana'];
const vegetables = ['carrot'];
const fruitsAndVegetables = [...fruits, ...vegetables]; // ['apple', 'orange', 'banana', 'carrot']
const fruitsAndVegetables = ['carrot', ...fruits]; // ['carrot', 'apple', 'orange', 'banana']
```

**4. Pass array items as arguments**

```
const mixer = (x, y, z) => console.log(x, y, z);
const fruits = ['apple', 'orange', 'banana'];

mixer(...fruits); // 'apple', 'orange', 'banana'
```

**5. Convert arguments to an array**

```
const mixer = (...args) => console.log(args);
mixer('apple'); // ['apple']
```

**6. Convert NodeList into an array**

```
[...document.querySelectorAll('div')];
```

**7. Copy an object**

```
const todo = { name: 'Clean the dishes' };
const todoCopied = { ...todo }; // { name: 'Clean the dishes' }
console.log(todo === todoCopied); // false
```

**8. Merge objects**

```
const todo = { name: 'Clean the dishes' };
const state = { completed: false };
const nextTodo = { name: 'Ironing' };
const merged = { ...todo, ...state, ...nextTodo }; // { name: 'Ironing', completed: false }
```

**9. Split an array into characters**

```
const country = 'USA';
console.log([...country]); // ['U', 'S', 'A']
```




## Use spread operator to avoid mutating objects (i.e. shallow copying)

```
const a = { name: 'Joe' };
const b = { ...a };
b.name = 'Jane';
console.log(b); // { name: "Jane" }
console.log(a); // { name: "Joe" }
```

👆 This works on objects of single-level depth. 
 

[Source](https://nick.scialli.me/object-assignment-for-beginners/)