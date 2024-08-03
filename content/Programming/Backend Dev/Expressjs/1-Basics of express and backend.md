The absolute basics can be followed from [Backend Development](../Backend%20Development.md). Backend deals with a bunch of [HTTP requests](../HTTP%20requests.md) and processes it with backend logic. There are [Middleware](../Middleware.md) involved if we need to process some things in between, before we process in the backend. 

- `app.use` is a method in Express.js that allows us to configure middleware for our application. Middleware functions have access to the request object (`req`), the response object (`res`), and the `next` function in the application's request-response cycle. 
- `app.listen` start the server that listens for incoming HTTP requests on a specified port. Without this the localhost is not 'on' and hence the app won't be running.

```js
app.listen(3000, () => {
  console.log('Server running on port 3000');
});

```

-  the use of [body-parser](../body-parser.md) module gives us access to `req.body` allowing better control of the request





