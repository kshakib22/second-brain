
You can declare using  `let` , `var`, or `const`.  Additionally, you can also implicitly declare without using any of these keywords. Implicit variables are also [[global]] variables, but can be prevented in [[strict]] mode. Read on [[hoisting]] to clear more confusions that arise due to declaration.

In terms of [[scope]], these are the differences: 
- `var` has function scope
- `let` has block scope
- `const` has block scope

```js
var x = 14
let foo = "bar"
const pi = 3.14

// Implicit
tuna = "tuni"
```


> [!NOTE] Note
> `use strict;` solves a lot of problem by eliminating implicit declaration

