# JavaScript Promises

_notes from Makers Promises workshop_

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


