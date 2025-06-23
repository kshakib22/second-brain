# Hoisting

Essentially gives the impression variables exist even *before* declaration.

 - Variables declared with `var` are hoisted to the top of their function scope, but their initialization remains where the code originally places it. Before initialization, the variable is `undefined`.
 -  Variables declared with `let` and `const` are also hoisted to the top of their block, but they are not initialized. Accessing them before declaration results in a `ReferenceError`.