
*Not recommended to use anymore - use `let` or `const` instead.* 👎

---
Used to declare variables within a function [[scope]]. Variables declared with **var** can be both
- updated
- re-declared 
It can also be just constructed, and the value would be `undefined`

```js
var myName = "Jane";
myName = "Shakib" // (Update) myName will return Shakib
var myName = "Impostor" // (Re-declare) this is allowed for vars

var whaT;
console.log(whaT) // returns 'undefined'

```
