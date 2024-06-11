`Math.random()` returns a floating-point number greater than or equal to 0, but strictly less than 1.

It utilizes an algorithm to generate these pseudo-numbers, but they are not truly random in a cryptographic sense. This means they can be predictable for certain applications.

## Getting a random number between 0 and x

The way to do this is to multiply the `Math.random()` with $x+ 1$ to scale it.

> [!Warning] Argument
> `Math.random()` does not take any arguments
 

```js
var num = Math.random()* (x+1)
```
