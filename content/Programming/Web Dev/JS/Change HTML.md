Using `innerHTML` method, we can literally change the HTML code for the element we query. This method will return the literal HTML code within the specific tag.
```HTML
<h1> <strong> Hello </strong> </h1>
```

```js
document.querySelector("h1").innerHTML;
// returns <strong> Hello </strong>
```

The following code will change the heading from bolded (strong) "Hello" to italicized "Bye Bye" by effectively changing the HTML code.
```js
document.querySelector("h1").innerHTML = <em> Bye Bye </em>;
```