Allows us to attach **event listeners** (essentially functions) to HTML elements in response to an 'event'. Events could be `click` for button clicks,  `"mouseover"`, `"mouseout"`, `"keydown"`, and many more.

First we obtain the element using [document.querySelector](document.querySelector.md) (or the whole document), then we call the event listener. It commonly takes two parameters - *event* and *function/listener*.
- event - corresponding event
- function/listener - to be run to perform a some behavior/change. 


> [!Warning] Function as a variable instead of a method
> This is function *without* brackets. Otherwise it will get triggered **without** the event which we don't want. Imagine function being passed as a *variable* and not a function/method.

This is somewhat similar to the idea of [[anonymous functions]]. Later we will see that in a lot of event listeners, anonymous functions are commonly used instead of named functions.

**Example: Changing Button Text on Click**

Here's an example of how to use `addEventListener` to change the text of a button when it's clicked:

```html
<button id="myButton">Click Me</button>

<script>
  const button = document.getElementById("myButton");

  button.addEventListener("click", function() {
    button.textContent = "Clicked!";
  });
</script>

```


#### Event passing to function

The 'event' that takes place, can also be passed to the function parameter of addEventListener.
```js
document.addEventListener("keydown", function (event) {

console.log(event);

});
```

In the example above, the whole document is being 'listened to' for `keydown` - which is whenever any key is pressed down. The function takes in a parameter called `event`. This is *specific event* that occurred to trigger the listener. If we print it out, we get a whole object containing info about the event, most importantly the **specific key that was pressed**. 