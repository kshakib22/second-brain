The absolute basics can be followed from [Backend Development](../Backend%20Development.md). Backend deals with a bunch of [HTTP requests](../HTTP%20requests.md) and processes it with backend logic. There are [Middleware](../Middleware.md) involved if we need to process some things in between, before we process in the backend. 

- `app.use` is a method in Express.js that allows us to configure middleware for our application. Middleware functions have access to the request object (`req`), the response object (`res`), and the `next` function in the application's request-response cycle. 
- `app.listen` start the server that listens for incoming HTTP requests on a specified port. Without this the localhost is not 'on' and hence the app won't be running.

```js
app.listen(3000, () => {
  console.log('Server running on port 3000');
});
```

-  the use of [body-parser](../body-parser.md) module gives us access to `req.body` allowing better control of the request


## Dynamic server side

After getting familiar with the basics of Express.js and middleware, we have encountered `res.sendFile()` for serving static files like HTML, CSS, or JavaScript. However, when we need to serve dynamic content—where the content of the HTML changes based on the data—we'll need something more powerful. This is where **[EJS](../EJS.md) (Embedded JavaScript)** comes into play.

- **res.render()** is used to send dynamic HTML pages. These pages can change based on variables, user input, or data retrieved from a database.
- Dynamic pages are useful for user dashboards, content management systems, e-commerce sites, etc., where content needs to adapt to the user or context.
- EJS is used for *server side rendering* where processing is done before it is sent back to user.

