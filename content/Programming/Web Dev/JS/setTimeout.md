 Schedules a function to be executed **after a specified delay** (in *milliseconds*). Useful for creating timed events, animations, or delaying code execution.
 
```js
//syntax
setTimeout(function, milliseconds)

// example
function sayHi() {
  alert("Hello after 3 seconds!");
}

setTimeout(sayHi, 3000);  // Execute sayHi after 3 seconds (3000 milliseconds)

console.log("This will be printed immediately!");


```
