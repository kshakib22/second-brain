A programming interface that allows programming elements to be modified and interactive. A standard structure allows us to access and modify elements in a predictable way.

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
	