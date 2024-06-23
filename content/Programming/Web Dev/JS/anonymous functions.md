Anonymous functions are functions in programming that **don't have a pre-defined name**. They are handy for concise code or one-time use cases. They are often stored in variables or passed as arguments to other functions. They can take inputs and return outputs just like named functions.

**Key points**
- No formal name assigned, hence "anonymous."
- Often stored in variables or passed as arguments to other functions.
- Can be passed around as arguments, allowing more flexibility


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