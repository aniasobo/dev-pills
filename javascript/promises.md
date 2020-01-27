# JavaScript Promises

Example use of different Promise syntaxes in React:

```
// async code; 'done' is logged after position data, even though 'done' is supposed
// to be executed later in our code

navigator.geolocation.getCurrentPosition(position => {
	console.log(position);
}, error => {
	console.error(error);
});
console.log("done");

// async code handled with a promise; we get the result we want - position data
// is logged, then 'done' is logged

const promise = new Promise((resolve, reject) => {
	navigator.geolocation.getCurrentPosition(resolve, reject);
});

promise
	.then(position => console.log(position))
	.catch(error => console.error(error))
	.finally(() => console.log('done'));

// async code with async/await looks like synchronous code; the most readable way 
// of  working with promises

async function getPosition() {
	
	// async/await works in functions only (for now)

		const result = await new Promise((resolve, reject) => {
	navigator.geolocation.getCurrentPosition(resolve, reject);
	});
		const position = await result;
		console.log(position);
		console.log('done');
}

getPosition();
```

Using basic Promise syntax vs async-await:

```
// fetching data from an API with basic promise syntax (notice the use of arrow functions)

window.fetch('http://jsonplaceholder.typicode.com/posts')
	.then(response => response.json())
	.then(data => console.log(data));

// fetching same data from API with async/await

async function getPostData() {
	const response = await window.fetch('http://jsonplaceholder.typicode.com/posts')

		// we need to resolve two promises using await to get the final data

	const data = await response.json();
	console.log(data);
}
getPostData();
```
   
[SOURCE](https://dev.to/codeartistryio/10-javascript-concepts-you-need-to-master-react-cheatsheet-3njh)

---

## Notes from Makers Promises workshop

`try-catch` = equivalent of Ruby `begin-rescue` - not a good way to handle errors; better - using JS promises.

sample code without promises:

```
$.ajax('file.json').done(function(){
	console.log('success');
	return $.ajax('file2.json')
	
}).done(function(){
	console.log('second success');
	return $.ajax('file3.json');
	
}).done(function(){
	console.log('third success');
	
	}).fail(function(){
	console.error('some error');
});
```


`$.ajax('file.json', {})` - AJAX request

[https://promisesaplus.com](https://promisesaplus.com)  

**keyword `then`**

`then` is the method that denotes that the function is a promise; first argument is the success, second is the fail. Called on a `new Promise()` object.

[Promises: states and fates](https://github.com/domenic/promises-unwrapping/blob/master/docs/states-and-fates.md):  

**The possible states (mutually exclusive):**

1. fulfilled
2. rejected
3. pending  

**The possible fates (mutually exclusive):**

1. resolved
2. unresolved

> A promise's state is reflected in its `[[PromiseState]]` internal slot.

> A promise's fate is stored implicitly as part of its "resolving functions."

## More resources:

* [Fun Fun Function Promises video](https://www.youtube.com/watch?v=2d7s3spWAzo)  
* [Wes Bos JS30 tutorials](https://javascript30.com/)
* [Promises in JS and Node video](https://www.youtube.com/watch?v=QujWZUYpeNk)


