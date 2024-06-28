
jQuery is a JavaScript library that simplifies DOM manipulation and event handling. The main idea of this library is to shorten verbose code while still making a lot of syntactic and semantic sense. 

jQuery historically has been the king of all packages as the most popular and used frameworks. So even though in modern days it might be slowly getting obsolete, there is still virtue in learning this framework especially as a beginner. 

An example of this is the following: 

```js
// typical JS code
document.querySelector("h1")

// jQuery equivalent
jQuery("h1")

// shorthand way (main)
$("h1")
```

#### Importing and Using jQuery

We can either download the library for use, or use [[CDN]] links to load the qQuery elements.
Then we use the `<script>` tag to load jQuery using the CDN. Paste this after HTML loaded, before the end of body and the JS file. Pasting it in `<head>` section might cause issues as JS might try to load before the jQuery is ready. There is a method in jQuery to make sure it's ready before JS is run, but that is a little too much work. Rather pasting it in this order is easier.

#### Basic stuff

Normal selection is done and augmented similar to `selectQuery` like :
```js
//space needed for nested properties
$(h2.title#id nested)
```


> [!warning] Multiple select
> The normal select `$("button")` selects ***all***  buttons through this single command. This means any change made using this command will change all the buttons.

Get/Change the css using the `.css` method after selecting the element. Get the property using a single argument, set it using the second argument. 
```js
// getting the value
console.log($("h1").css("font-size"));

//Direct change using .css(property, value)
$("h1").css("color", "red");
```

Add a class using `.addClass` method, remove using `.removeClass` method. Separate mutiple classes to be added/removed using a *space* . 

```js
// Add class
$("h1").addClass("big-text");

// remove 
$("h1").removeClass("big-text");
```

Text is edited using `.text` method, innerHTML is edited using `.html`

```js
$("h1").text("New heading");
$("button").html("<em>Click<em>");
```

Attributes within elements of HTML can be edited using `.attr`. Setting, once again, is done by passing two arguments.

```js
// getting href within anchor tag
$("a").attr("href");

// changing href within anchor tag
$("a").attr("href", "bing.com");
```

#### Event Listener 

Events are apparently methods in jQuery. For example, for clicks there is `.click` method. Keydowns are `.keydown` too. 

```js
$("button").click(function(){
	// callback function stuff
})
```

Similar to selectors in JS, we can select the whole document and make changes too. Document is selected without using "quotes".
```js
// code to show key pressed in heading
$(document).keydown(function (event) {
	$("h1").text("test");
});
```

#### Dynamic Addition/Removal

We can add HTML using `.before`, `.prepend` and `.after`, `.append`. Difference between 'before' and 'prepend' is that before implied HTML added *before* the element mentioned. Prepend adds HTML within the element, but at the beginning of whatever it contains. Similar idea for after, append.

Just using `.remove()` removes all instances of that element.

#### Basic Animation

**1. The `animate()` Method:**

The core functionality for animations comes from the `animate()` method. It allows you to animate various CSS properties of an element over a specified duration.
```js
$(selector).animate({ properties }, [speed], [callback]);
```
- **`selector`:** This identifies the element(s) you want to animate using jQuery syntax (e.g., `#myElement`, `$(".myClass")`).
- **`properties`:** This is an object that defines the CSS properties you want to animate. Key-value pairs specify the property name and its target value (e.g., `{ opacity: 0.5, left: '200px' }`).
- **`speed` (optional):** This defines the animation speed. It can be a string value ("slow", "medium", "fast") or the duration in milliseconds (e.g., 1000 for 1 second).
- **`callback` (optional):** This is a function that gets executed after the animation completes (useful for chaining animations).

**2. Available Properties:**

You can animate various CSS properties using `animate()`. Here are some common examples:

- `opacity`: Controls transparency (0 for fully transparent, 1 for fully opaque)
- `left`, `top`, `right`, `bottom`: Positions the element
- `width`, `height`: Change the size of the element
- `backgroundColor`: Animate the background color
- `margin`, `padding`: Modify margins and paddings

**3. Chaining Animations:**

You can chain multiple animations together to create more complex effects. The `callback` function allows you to define what happens after one animation finishes before starting the next.

**4. Additional Effects:**

jQuery also provides other animation methods like `fadeOut()`, `fadeIn()`, `slideToggle()`, etc., that offer pre-defined animations for common use cases.

Explore the jQuery documentation for a comprehensive list of animation methods and properties: [w3schools jQuery Animate](https://www.w3schools.com/jquery/jquery_animate.asp)
