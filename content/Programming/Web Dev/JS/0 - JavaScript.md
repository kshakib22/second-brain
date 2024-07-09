This is my basic JS starting point. This page gives a general overview of JS and links to relevant topics to study further if needed.

## Introduction

JavaScript (JS) is a high-level, versatile programming language that is a core technology of the World Wide Web, alongside HTML and CSS. It is essential for creating interactive and dynamic user experiences on websites. Initially developed to make web pages interactive, it has since grown into a language used for full-scale web applications, server-side development, and even mobile app development.

## Working within a browser

For chrome, use developer tools `->` sources. Then within submenu select Snippets. It will show `index.js `  on the left where we can add JS scripts to see how it affects browser behavior. Then press `⌘+Enter` to run.

## Quick Overview

The notes don't go into too much details considering some existing programming knowledge. Maybe at different points it will be compared to existing knowledge (mainly [[Python]]). JavaScript is also dynamically typed, with similar data structures. One key difference between them is Python is [[Object-Oriented]] while JS is [[Prototype based]]. 

Here is the primitive data types - which are also inherently [[immutable]]. A lot of them have their own methods too.
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
Multiple conditionals are combined using **&&** for AND and **||** for OR.

[[alert]] (message) -  brings up a pop up with the message
[[prompt]] (message) - brings up a pop up with message that can take an input 

## Compilation

JS is neither [[interpreted]] nor [[compiled]] but uses a mix of both known as just-in-time ([[Just-In-Time]]) compiled language.

Move to [[1 - JavaScript in HTML basics]] to have a gentle intro in context of JS as a script.