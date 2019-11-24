# Pros and cons of WebAssembly

## Pros

* speed and performance - better than JS
* works with all browsers
* near-native performance for CPU-heavy tasks


## Cons

* no direct access to the DOM
* freakin' HARD


## What is it good for?

* can be used on existing web apps to improve load time - good practice to replace only the code that does a lot of computation in a web app with WebAssembly
* any desktop applications
* intended as [compilation target of other languages](https://github.com/appcypher/awesome-wasm-langs); good for C, C++, Go, Rust - AssemblyScript when you don't want to learn the above
* Games
* Scientific visualization and simulation
* CAD applications
* Image/video editing