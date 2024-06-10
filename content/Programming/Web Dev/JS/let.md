Recommended method to declare variables/objects.

---
Used to declare variables in a block scope. Out of curly braces, out of mind. Variables declared with **let** 
- can be changed later on
- **cannot** be re-declared
Just constructing the variable gives it `undefined` value

```js
let pizza = "Pizza"
pizza = "Much Bigger Pizza" // Allowed
let pizza = "Burger" // Not allowed, Syntax Error
```