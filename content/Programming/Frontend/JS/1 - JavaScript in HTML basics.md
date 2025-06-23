
- **Inline:** JavaScript code written directly within HTML tags (e.g., `onclick` attribute or inside `<body onload ="">` . Highly unlikely to use.

- **Internal Script:** JavaScript code placed within [script](../HTML/script.md) tags inside the HTML document (`<head>` or `<body>`). Also unlikely to use
```html
<!DOCTYPE html>
<html>
<head>
  <title>My Page</title>
</head>
<body>
  <script>
    // Your JavaScript code here
    alert("This is inline JavaScript!");
  </script>
</body>
</html>
```

- **External:** JavaScript code stored in a separate `.js` file and linked to the HTML document using a `<script>` tag with `src` attribute. Goes into `<head>` like links. Usual method of scripting.
```html
<!DOCTYPE html>
<html>
<head>
  <title>My Page</title>
  <script src="myScript.js"></script>  </head>
<body>
  </body>
</html>
```

HTML is treated as a *document* with different levels of hierarchy/relationships. This is known as Document Object Model ([[DOM]]). Using DOM we can extract different portions of the HTML (document) and treat them as object to dynamically change them. 

Styling changes can be achieved after these elements have been extracted using [document.querySelector](document.querySelector.md). We can either change the HTML directly or change the CSS styling to make interactive changes. Check [Change Styling](Change%20Styling.md) where the different methods are mentioned. Once all these have been reviewed and understood, move to [2- Advanced JS and DOM Manipulation](2-%20Advanced%20JS%20and%20DOM%20Manipulation.md). 