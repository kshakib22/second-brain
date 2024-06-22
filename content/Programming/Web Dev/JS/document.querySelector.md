This is  a versatile tool for *pinpointing* specific elements within the DOM based on powerful **CSS** selectors. It offers more control and flexibility compared to methods like `document.getElementById` or `document.getElementsByTagName`.

**Function:**
- It takes a single argument, which is a **CSS selector string**. This selector defines the criteria for matching elements within the DOM.
- **Return Value:** It returns a reference (object) to the **first** element that matches the specified CSS selector. If no matching element is found, it returns `null`.


> [!warning] Multiple matches
> Remember the return value is just the **first** element. To deal with multiple selections, we use
> a different method [[document.querySelectorAll]]


The argument for the function can combine selectors as well such as 
`document.querySelector("li a")`  or `document.querySelector("li.item")`

In the above example, there is a space between `li` and `a` because the anchor tag (child) is within the list (parent) tag, but they are still different tags. But `li.item` has no space because item is the class, *within* the same tag of list. 

So a **space** $\rightarrow$ Hierarchical selection (in terms of DOM)
**No space** $\rightarrow$ Select within the element