The main ways to change styles are directly changing class elements or manipulating class/id that are part of the elements. We get the current list of classes using [classList](classList.md). 

### Directly Change CSS elements

Use [style](style.md) to change specific elements but changing their CSS properties
```js
document.querySelector("button").style.backgroundColor = "red";
```

### Change classes for elements

This is especially useful if you want multiple changes to an element through one run of code. We can add/remove/toggle to reflect these changes

1.  **Add CSS class**
We can add CSS class (that have been defined in CSS sheet) to change the behavior of the current *element* that we select. This can be achieved by adding to the list we get from [[classList]]. We use `classList.add()` to existing elements.

```js

var element = document.querySelector("h1"); //Could be any element like 'button'

element.classList.add("huge-red"); // Makes h1 huge red and bold

```

```css
huge-red {
font-size : 10rem;
color: red;
font-weight : bold;

}
```

In the above example, the script will turn the `<h1>` tag invisible by adding the class 'invisible' to it.

2. **Toggle CSS class**

From the above CSS example, we can keep toggling between visible and invisible using this - 
```js
var element = document.querySelector("h1"); //Could be any element like 'button'

element.classList.toggle("huge-red"); // Toggles between normal and huge-red
```

3. **Removing a CSS Class:**

 Use `classList.remove("class-name")` to remove a specific class from the element.

```js
var element = document.querySelector("h1"); 

element.classList.add("huge-red"); // Adds the "huge-red" class (assuming it wasn't there before)

// Later in your code, you might want to remove the class
element.classList.remove("huge-red");  // Removes the "huge-red" class

```
