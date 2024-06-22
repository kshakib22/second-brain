
This method serves as a net to capture all elements with a particular HTML tag name within your document.

> [!NOTE] Note
> This has 'Elements' in function name, implying the return of a multiple elements (an array)

**Function:**
- It takes a single argument, which is a **string representing the HTML tag name** you want to target (e.g., "p", "div", "h1").
- **Return Value:** It returns an **HTMLCollection** *object*, which is an array-like collection of all the elements in the DOM that match the specified tag name.

This means to change the individual elements within the returned list, we need to use [ ] to access specific item within the list.