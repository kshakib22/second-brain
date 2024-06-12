
## Working within a browser

For chrome, use developer tools `->` sources. Then within submenu select Snippets. It will show `index.js `  on the left where we can add js scripts to see how it affects browser behavior. Then press `⌘+Enter` to run.

## Quick Overview

The notes don't go into too much details considering some existing programming knowledge. Maybe at different points it will be compared to existing knowledge (mainly [[Python]]). JavaScript is also dynamically typed, with similar data structures. One key difference between them is Python is [[Object-Oriented]] while JS is [[Prototype based]]. 

Here is the basic data types. A lot of them have their own methods too.
- [[String]]
- [[Number]] - technically int and float considered same type here
- [[Boolean]] - true or false
- [[Undefined]] - value not assigned yet
- [[Null]] - absence of value altogether

Check datatype using the function  `typeof()` (built-in)
[[var]] - is a keyword used to [[declare]] *variables* 
Declaration done using `=`, comparison done using both `==` and `===` . Check [[Comparison Operators]] to clarify the differences.


Both `i++` as well as `i+=` is allowed in Javascript. 
`return` works the same as Python.
Use`//` for inline comment and `/* shizle goes here */` for comment snippet

Check [[Functions]] for overview and syntax for functions.
Check [[Control Flow]] for notes on loops and conditionals.

[[alert]] (message) -  brings up a pop up with the message
[[prompt]] (message) - brings up a pop up with message that can take an input 

## Compilation

JS is neither [[interpreted]] nor [[compiled]] but uses a mix of both known as just-in-time ([[Just-In-Time]]) compiled language.