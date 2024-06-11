## Template Literals (substitution)

Substitution is done using what is called template literals which provides template to substitute values into. This is done by using backticks (not single quote) to enclose the string. We also need this format for the substitution `${varName}` inside the string.

```js
const name = "Skib";
const time = 0;

const greeting = `Hello, ${name}! You are ${time} days from losing it all!`;
console.log(greeting); // Hello, Skib! You are 0 days from losing it all!

```
