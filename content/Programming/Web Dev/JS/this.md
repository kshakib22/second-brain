When we use `addEventListener` to attach an event listener to an element, the value of the keyword `this` inside the event handler function becomes a reference to the element that triggered the event.

This means the triggered element can now be directly accessed and processed without needing other ways to access this specific element.

```js
button.addEventListener("click", function() {
  this.textContent = "Clicked!"; // Changes the button text
});

```

In the above example `this` refers to the button element. If we had done something like this - 
```js
document.addEventListener("keydown", function (event) {
console.log(this);
});
```

then `this` here actually represents the `document` itself which is the whole HTML.