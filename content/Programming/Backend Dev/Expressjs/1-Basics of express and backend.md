The absolute basics can be followed from [Backend Development](../Backend%20Development.md). Backend deals with a bunch of [HTTP requests](../HTTP%20requests.md) and processes it with backend logic. There are [Middleware](../Middleware.md) involved if we need to process some things in between, before we process in the backend. 

- `app.use` is a method in Express.js that allows us to configure middleware for our application. Middleware functions have access to the request object (`req`), the response object (`res`), and the `next` function in the application's request-response cycle. 
- `app.listen` start the server that listens for incoming HTTP requests on a specified port. Without this the localhost is not 'on' and hence the app won't be running.

```js
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

-  the use of [body-parser](../body-parser.md) module gives us access to `req.body` allowing better control of the request
- this body-parser is also supported by express natively
```js
// Instead of this:
// const bodyParser = require('body-parser');
// app.use(bodyParser.urlencoded({ extended: true }));

// Use this:
app.use(express.urlencoded({ extended: true }));
```

**Accessing the data**:
- To get data from user input to the server (for example, HTML form variables) we use POST method, along with `req.body["variableName"]`
- We can also access using dot operator, for example:
```js
app.post('/submit', (req, res) => {
  // Accessing properties from req.body
  const name = req.body.name;  // assuming req.body contains a property 'name'
  const age = req.body.age;    // assuming req.body contains a property 'age'

  // You can now use these properties
  res.send(`Name: ${name}, Age: ${age}`);
});
```


## Basic Structure of `app.post` and `app.get`
- **`app.post`** and **`app.get`** are methods in Express.js used to define routes for handling HTTP POST and GET requests, respectively.
- Both methods take at least two parameters:
  1. **Route Path (`string`)**: The URL path for the route.
  2. **Callback Function (`function`)**: The function to execute when the route is matched.

### Callback Function Parameters
- The callback function for both `app.post` and `app.get` typically takes the following parameters:
  - **`req` (Request Object)**: Contains information about the HTTP request, including:
    - **`req.body`**: Data sent by the client in the body of a POST request.
    - **`req.query`**: Query string parameters in the URL for GET requests.
    - **`req.params`**: Route parameters.
    - **`req.headers`**: Request headers.
  - **`res` (Response Object)**: Used to send back the desired HTTP response.
  - **`next` (Function)**: Optional, used to pass control to the next middleware function.
## Dynamic server side

After getting familiar with the basics of Express.js and middleware, we have encountered `res.sendFile()` for serving static files like HTML, CSS, or JavaScript. However, when we need to serve dynamic content—where the content of the HTML changes based on the data—we'll need something more powerful. This is where **[EJS](../EJS.md) (Embedded JavaScript)** comes into play which can inject JS code into HTML.

- **res.render()** is used to send dynamic HTML pages. These pages can change based on variables, user input, or data retrieved from a database.
- Dynamic pages are useful for user dashboards, content management systems, e-commerce sites, etc., where content needs to adapt to the user or context.
- EJS is used for *server side rendering*  where processing is done before it is sent back to user.
- Pay attention to how JS loops are written line-by-line in EJS and how curly braces are closed.


> [!Important] General Idea
> **User $\rightarrow$ Server** : Using HTML and JS
**Server $\rightarrow$ Server** Using POST to send `req.body` or other data from express in JS to EJS
**Server $\rightarrow$ User** : Using EJS templating for JS *within* the HTML

Visualizing the flow:
```
User (Browser) -> Submit Form -> Server (Express.js)
   |
   | (Form Data in HTTP Request)
   |
   v
Server (Express.js) -> Process Data -> EJS Template
   |
   | (Generate Dynamic HTML)
   |
   v
Server (Express.js) -> Send Response (Rendered HTML) -> Browser
   |
   | (Display Updated Page)
   |
   v
User (Browser)
```

Look up how folder is structures in EJS projects at [EJS folder structure](../EJS%20folder%20structure.md). 
- The `app.use(express.static("public"))` line in an Express.js application serves static files like images, CSS, JavaScript, etc., from the public directory.

After understanding basics of HTTP requests, dealing with these requests and its data, dynamic server-user data transfer, we move to learning basics of [Application Programming Interfaces (APIs)](2%20-%20Application%20Programming%20Interfaces%20(APIs).md). 