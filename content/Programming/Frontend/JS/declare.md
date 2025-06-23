
You can declare using  `let` , `var`, or `const`.  Additionally, you can also implicitly declare without using any of these keywords. Implicit variables are also [[global]] variables, but can be prevented in [[strict]] mode. Read on [[hoisting]] to clear more confusions that arise due to declaration.

> [!NOTE] Note
> `use strict;` solves a lot of problem by eliminating implicit declaration

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


> [!warning] Common confusion

`const` doesn't allow re-assignment. But it *does* allow changing individual elements.

```js
const array = [1,2,3,4,5,6,6,6]

array[0] = 10 // allowed

array = [4,2,0] // ERROR, not allowed
```


