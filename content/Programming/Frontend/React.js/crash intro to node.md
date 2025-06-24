

1. `ReactDOM.createRoot` is a method introduced in React 18 that enables the new Concurrent Mode, allowing React to work more efficiently and prepare for future features like selective rendering and transitions.
	- `render` takes only one HTML element. Therefore for multiple components, it's easier to combine a couple things into a `<div>` which treats the whole thing as a single div.

2. JSX is essentially a JS file. Through node we are injecting HTML. So we can further inject JS code into that HTML as well
	- The JS is inserted into the HTML using *curly braces* `{}`

3. In JSX, you can write JavaScript expressions (like `2 + 2`, `user.name`, or `ternaries`), but not full statements (like if, for, while, etc.).
   
4. Template literals are also supported. 

```js
const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
```

5. Script type in HTML file should be `JSX` instead of the usual javascript
6. The CSS class name is usually `class="cname"` but for JSX it is `className = "cname"`
7. The class names are the same as HTML *global* ones, but in **Camel case**. For example, `contenteditable` in HTML becomes `contentEditable` in JSX.