
Strings in JS are slightly similar to [Python](Python.md) .  In both cases they are **[[immutable]]** and even though it supports `[]` element access, there is no way to change existing string.

Key similarities:
- You can concatenate using '+' 
-  You can concatenate string in quote with a variable containing string using '+'
- 'text' and "text" essentially same and interchangeable
- **Backticks** also work to declare string. Or rather define a *[[template literal]]*  for string formatting

## Slicing

There is an in-built method for slicing strings. The method uses dot operator `.slice()`  on string variables. The parameters passed behave similar to [[range]] in Python. The first param is the starting index, and the last param is the index where it stops (non inclusive).

```js
let x = "myName"
x.slice(0) // returns "myName" because if end not mentioned, goes till it ends
x.slice(-1) // returns "e"
x.slice(0:4) // returns "myNa"
```

Check [[Square Brackets]] to see how they behave in different iterables.

# Other Methods

The method `.toUpperCase()` turns the string into upper case. Example use case - ALERTS, first letter capitalization, etc.

The method `.toLowerCase()` turns string into lower case. Example use case - data consistency for processing.