After accessing elements by either ID, class, or query selector, we use .style operator to edit CSS styling. However, the names of CSS properties are not the same as the JS properties name for the same thing. Follow this [link](https://www.w3schools.com/jsref/dom_obj_style.asp) to get reference to their property names equivalent in JS.

For example changing the background color of a "button" class:

```js
document.querySelector("button").style.backgroundColor = "red";
```