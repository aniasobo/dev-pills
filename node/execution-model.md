# Node execution model - synchronous and asynchronous operations, blocking and non-blocking operations  

**Every synchronous operation in Node results in a blocking operation** (even `console.log()`).  

The event loop in pseudocode:

```
while (I still have stuff to do) {
  do stuff;
};
```

## Key takeaways:

* Node loops for as long as asynchronous operations are ongoing
* IO operations are expensive, so they should be handled using asynchronous operations
* the code within the synchronous loop needs to be as lean as possible
* handle CPU-expensive operations with Event Emitters
    
           
Source: Manuel Kiessling's [Node Craftsman](https://leanpub.com/nodecraftsman) book