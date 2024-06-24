The basic notation of control flow in JS involves `()` for any logical condition/expression and `{}` to indicate what to do for that logic. Examples are given below.
1. **if, else if, else**

```js
if (condition) {
  // code to execute if condition is true
} else if (otherCondition) {
  // code to execute if otherCondition is true
} else {
  // code to execute if none of the conditions are true
}
```

2.  **switch**

Remember that in the beginning `{` is used for separation. However, for cases, we use `:`. The values refer to the value of `expression`. If none of them are satisfied, default is performed.
```js
switch (expression) {
  case value1:
    // code to execute if expression === value1
    break;
  case value2:
    // code to execute if expression === value2
    break;
  default:
    // code to execute if expression doesn't match any case
}
```

3. **for** loop
```js
for (initialization; condition; update) {
  // code to execute repeatedly while condition is true
}

for (let i = 0; i < 5; i++) {
    console.log("Iteration:", i);
}

// Output:
// Iteration: 0
// Iteration: 1
// Iteration: 2
// Iteration: 3
// Iteration: 4

```

4. **while** loop
```js
while (condition) {
  // code to execute repeatedly while condition is true
}
```

5.  **do...while** Loop
```js
do {
  // code to execute at least once, and repeatedly while condition is true
} while (condition);

```

6. **for...of** Loop - This is commonly used with basic iterable data structures such as Arrays, strings, sets, maps, etc.
```js
for (const element of iterable) {
  // code to execute for each element in the iterable
}

const colors = ["red", "green", "blue"];
for (const color of colors) {
    console.log(color);
}

// Output:
// red
// green
// blue

```

7. **for...in** Loop - This is commonly used for *Objects* (including arrays, but generally used for object properties)
```js
for (const key in object) {
  // code to execute for each key
}

const person = { name: "Alice", age: 30 };
for (const key in person) {
    console.log(key, ":", person[key]);
}

// Output:
// name : Alice
// age : 30

```

8. **break and continue** 
- **break**: Exits the loop or switch statement immediately.
- **continue**: Skips the current iteration and proceeds to the next iteration of the loop.
```js
for (let i = 0; i < 10; i++) {
  if (i === 5) {
    break; // exits the loop when i is 5
  }
  if (i % 2 === 0) {
    continue; // skips the current iteration if i is even
  }
  console.log(i); // prints odd numbers less than 5
}
```
