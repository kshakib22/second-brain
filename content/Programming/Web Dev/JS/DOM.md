A programming interface that allows programming elements to be modified and interactive. A standard structure allows us to access and modify elements in a predictable way. It has similar feeling to [[OOP]], where document is an object with properties and methods (that involve both getting and setting).

### Structure

- The DOM treats the whole page as a document. 
	- This `document` is the root element, also used in JavaScript.

- Each branches represent elements like `<div>` `<h1>`, `<p>`, etc
	- The leaves are the content within these tags such as text

- Elements can have attributes, such as `id` or `class` based on the HTML

### Access

- Elements can be accessed through `id` , `tag`, or `class`
	- `document.getElementById("myElement")`
	- `document.getElementsByTagName("p")`
	- `document.querySelector(".myClass")`

Check [[document.getElementById()]], [[document.getElementsByTagName()]], [[document.querySelector]], [document.querySelectorAll](document.querySelectorAll.md)

> [!NOTE] Query Selector
> Most commonly, querySelector is used instead of getting by ID or Element due to its flexibility.
> For getting all of them, querySelectorAll is used.


### Changing styling

To change css styles, we can use [[style]] after accessing elements. But this will change a *single* property at a time. What if we want to change a whole class or add a whole class?

Check out [[Change Styling]] to see different ways to achieve this.

### Changing text content

Can be done essentially in two ways - 
1. Change the literal text content : uses `.textContent` method
2. Change the literal HTML code : uses `innerHTML`;  check [[Change HTML]]

### Changing attribute 

In this process, we select a certain element/tag first. Within HTML elements, they can have different types of attributes which can also be changed to reflect changes. Check [[Change Attributes]] on how to do this.


### Next Up

Once the DOM model makes sense, look at [[2- Advanced JS-DOM Manipulation]] for things like dynamic changes to clicks and other events.
