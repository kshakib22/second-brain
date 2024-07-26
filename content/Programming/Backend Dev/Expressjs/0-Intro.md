**Express.js** is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. It simplifies the process of building *server-side* applications using Node.js. This means handles requests from the client, processes data, and sends responses back.

- **Simplicity:** It provides a streamlined way to handle HTTP requests and responses.
- **Routing:** It helps define different routes for your application, like different pages or API endpoints.
- **Middleware:** It allows you to add custom functions (middleware) to process requests and responses.

When we start an Express.js server, it listens on a specified port for incoming HTTP requests. The server is usually run on [localhost](../../Web%20Dev/localhost.md) during development to test the application. Look into [HTTP requests](../HTTP%20requests.md) to learn about the basic requests a server deals with.

The following code handles the GET request to the root URL (simply contains `"/"` without anything being followed). 

`app.get(”/”)`:
- Sets up an HTTP GET route for the root URL ("/").
- When a client sends a GET request to the root URL, this route is triggered.

`(req, res) => {…}`:
Callback function that handles the request and response.
- req: Represents the incoming request object.
- res: Represents the outgoing response object.

Details on `(req, res)` is at [[Request and Response in Express]] . Check [arrow function](arrow%20function.md) for this type of function definition style.

```js
app.get("/", (req,res) => {
	console.log(req);
});
```

