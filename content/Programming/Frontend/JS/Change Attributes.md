Attributes within certain elements can be changed as well.

### Viewing attributes

Firstly, to view the attributes present in an element, we use 
```js
document.querySelector("a").attributes;
```
This returns an array-like object that holds individual attribute objects within the element. We *do not* modify using `attributes` this is just to see what's there.


### Getting attributes

We use a getter method for this - 
```js
document. querySelector("a").getAttribute("href");
// returns "https://www.website.com"
```

### Changing/Setting attributes

We use `setAttribute` method that takes two arguments -
1. attribute to be changed
2. new value
```js
document. querySelector("a").setAttribute("href", "www.bing.com");
```

