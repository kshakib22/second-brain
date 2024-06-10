# Scope

JavaScript has three types of scopes: **global scope**, **function scope**, and **block scope**. Connects to [[var]], [[let]], and [[const]]. Read on [[hoisting]] to clear more confusions that arise due to declaration.

#### 1. Global Scope

Variables declared outside any function or block have global scope. They can be accessed from anywhere in the code. This can be declared using either of `var`, `const`, or `let`. 

```js
var globalVar = "I'm a global variable";

function testGlobal() {
    console.log(globalVar);  // Accessible here
}

testGlobal();
console.log(globalVar);  // Accessible here too

```

#### 2. Function Scope

Variables declared inside a function with `var` are scoped to the function. They cannot be accessed outside the function.
```js
function testFunctionScope() {
    var functionScopedVar = "I'm a function-scoped variable";
    console.log(functionScopedVar);  // Accessible here
}

testFunctionScope();
console.log(functionScopedVar);  // Uncaught ReferenceError: functionScopedVar is not defined

```

#### 3. Block Scope

Variables declared inside a block (a pair of curly braces `{}`) with `let` or `const` are scoped to that block. They cannot be accessed outside the block. The example below doesn't even use a function, it uses an if condition.

```js
if (true) {
    let blockScopedVar = "I'm a block-scoped variable";
    const anotherBlockScopedVar = "I'm also a block-scoped variable";
    console.log(blockScopedVar);  // Accessible here
    console.log(anotherBlockScopedVar);  // Accessible here
}

console.log(blockScopedVar);  // Uncaught ReferenceError: blockScopedVar is not defined
console.log(anotherBlockScopedVar);  // Uncaught ReferenceError: anotherBlockScopedVar is not defined

```

#### var vs. let

This is where it gets tricky/confusing. The best way to remember this is through few examples. In general, don't use `var` unless for some reason really required.

This example shows the difference between [var](var.md) and [[let]] . Or in other words, function scope and block scope.

```js
function myFunction() {
    let x = 10;  // x is block-scoped to the function block
    if (true) {
        let y = 20;  // y is block-scoped to the if block
        console.log(x);  // 10, accessible within the function block
        console.log(y);  // 20, accessible within the if block
    }
    console.log(x);  // 10, still accessible within the function block
    // console.log(y);  // Uncaught ReferenceError: y is not defined
}

myFunction();

```

The following example shows why `var` gets confusing and should be avoided. 

```js
var items = ['apple', 'banana', 'cherry'];

for (var i = 0; i < items.length; i++) {
    console.log('Inside loop:', i, items[i]);
}

console.log('Outside loop:', i);  // i is accessible here and its value is items.length which is 3 in this case
```

Firstly loop stops when `i` is 2 but its incremented to 3 so it prints as such. As it was not bound by any functions, it kinda behaves as a global variable being accessible anywhere.