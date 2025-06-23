Script can contain javascript code without needing quotation marks. Below is a simple example:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Script Tag Example</title>
  <script>
    function greet() {
      alert("Hello from the script tag!");
    }
  </script>
</head>
<body>
  <h1>Click the button to say hello</h1>
  <button onclick="greet()">Greet</button>
</body>
</html>

```

This example however is calling a function. Notice that the script is usually called *after* the HTML elements have been set. This provides a base on which *changes* can be applied.