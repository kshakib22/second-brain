In JavaScript, [[addEventListener]] is a powerful method that allows you to attach **event listeners** to HTML elements. It essentially creates a watch on a specific element, waiting for a particular event (like a click) to occur. When the event happens, the provided *function* (called the event handler) is executed, enabling you to perform actions in response to user interaction.

Using  `addEventListener` we can attach this listener to an element. When attached, we can use [anonymous functions](anonymous%20functions.md) along with [this](this) keyword to make changes to that element directly.  If a specific function is passed to `addEventListener`, then it becomes a [Higher-Order Function](Higher-Order%20Functions.md). These are known as [callback functions](callback%20function.md) and they can take in arguments as well. One of the common argument it takes is the `event` argument.

To make changes in styling that simulates an animation, make styling changes (check [Change Styling](Change%20Styling.md)) and then use [[setTimeout]] to revert back to original state after a specific time. 

Check [[OOP in JavaScript]] for objects/constructors etc. Everything in JS is basically flexible, mutable objects and both properties and methods for an object can be added at anytime. It is essentially [Prototype based](Prototype%20based) language, which has a number of significant differences compared to traditional OOP.

Once basic JS and DOM manipulation have been completed, take a look at the [brief overview of jQuery](../jQuery%20Basics.md) where basics of jQuery is shown to make DOM manipulation much easier and less verbose. After that move to [Introduction to NodeJS](../Nodejs/0-NodeJS.md) for backend stuff.

