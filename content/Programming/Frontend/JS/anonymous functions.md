Anonymous functions are functions in programming that **don't have a pre-defined name**. They are handy for concise code or one-time use cases. They are often stored in variables or passed as arguments to other functions. They can take inputs and return outputs just like named functions.

**Key points**
- No formal name assigned, hence "anonymous."
- Often stored in variables or passed as arguments to other functions.
- Can be passed around as arguments, allowing more flexibility

```js
const arr = [1, 2, 3];
const doubled = arr.map(function (num) {
  return num * 2;
});
console.log(doubled); // [2, 4, 6]
```
<div style="text-align: center">
  Example of anonymous regular function
</div>

For the following example, check [anonymous functions](anonymous%20functions.md) for more.
```js
const arr = [1, 2, 3];
const doubled = arr.map((num) => num * 2);
console.log(doubled); // [2, 4, 6]
```
<div style="text-align: center">
  Example of anonymous arrow function
</div>

For the following example, check [callback function](callback%20function.md) for more.
```js
// Array of numbers
const numbers = [1, 2, 3, 4, 5];

// Using an anonymous callback function with the .map() method
const doubled = numbers.map(function(num) {
  return num * 2;
});

console.log(doubled); // Output: [2, 4, 6, 8, 10]
```
<div style="text-align: center">
  Example of anonymous callback function
</div>





## Use Cases

- **Event Listeners (JavaScript):** Anonymous functions are frequently used as event handlers in `addEventListener`.
-  **Higher-Order Functions:** Many [[Higher-Order Functions]] (HOF) rely on anonymous functions as arguments.
- **Callbacks:** They are often employed as callbacks in asynchronous programming, where a function is passed as an argument to be executed later.
- **Sorting and Filtering:** Anonymous functions can be used to define custom sorting or filtering criteria for data.

### Even Listener

Here the event listener uses an anonymous function and the keyword [[this]].
```js
const button = document.getElementById("myButton");

button.addEventListener("click", function() {
  console.log(this); // This will log the button element itself
});

```


