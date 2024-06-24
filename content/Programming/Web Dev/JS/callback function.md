A callback function is a function passed as an **argument** to *another function*. The receiving function (often called the higher-order function) then invokes the callback function at some point during its execution.

```js
function greet(name, callback) {
  console.log("Hello,", name);
  callback(name); // Call the callback function
}

function sayGoodbye(name) {
  console.log("Goodbye,", name);
}

greet("Alice", sayGoodbye);  // Pass sayGoodbye as a callback

// Output:
// Hello, Alice
// Goodbye, Alice

```

**Benefits:**
- **Flexibility:** Enables customization of behavior within a function.
- **Asynchronous Programming:** Allows functions to execute tasks and then call another function when finished.
- **Code Reusability:** Promotes modularity by separating concerns.
