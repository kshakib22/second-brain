
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
> The normal select `$("button")` selects ***all*** buttons through this single command

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

Text is edited using `.text` method, innerHTML is edited using 