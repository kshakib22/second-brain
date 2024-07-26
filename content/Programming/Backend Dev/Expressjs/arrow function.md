Arrow functions provide a *concise* way to write functions. Main purpose is to write a function **within** a function without having to declare it outside and call it.

`(parameters) => { statements }`

•	Single-line arrow functions don’t need curly braces or a return statement.

```js
const add = (a, b) => a + b;
```

•	Arrow functions do not have their own `this` context; they inherit this from the parent scope.
```js
function Person() {
  this.age = 0;
  setInterval(() => {
    this.age++; // `this` refers to the Person instance
  }, 1000);
}
const p = new Person();
```

•	Arrow functions cannot be used with the new keyword.
