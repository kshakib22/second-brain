Middleware in web development generally refers to **middleware functions** that acts as a **bridge** between database and applications, especially on a network. It is a key part of backend development, handling various tasks between the client and the server.

- **Request and Response Handling**: Middleware functions typically handle HTTP requests and responses, processing them *before* they reach the server’s core logic or before the responses are sent back to the client.
- **Pre-Processing**: Middleware can perform operations such as logging, authentication, and session management, transforming the request object before it reaches the main application logic.
- **Post-Processing**: Middleware can also modify the response object before sending it back to the client, for example, formatting data, adding headers, or compressing responses.
- **Authentication**: Verify whether request is allowed before we process them.


> [!NOTE] Accessing `req, res, next()`
> When we define a middleware function in Express, it *automatically* gets the `req`, `res`, and `next` parameters from the Express framework.

Middleware functions are executed sequentially in the *order they are defined* in the application. Each middleware function **must** either:
- Call `next()` to pass control to the next middleware function.
- End the request-response cycle (e.g., by sending a response).


> [!warning] Function parameters
> Even if a middleware function doesn’t use `res` or `req`, the function signature must include all three parameters (`req`, `res`, `next`). This is because Express expects middleware functions to adhere to this signature to work correctly.


**Benefits:** By introducing a middleware, we allow for *separation of concerns*, making the codebase more modular and maintainable. Middleware functions can be reused across different parts of the application or even in different projects. This also facilitates scaling by allowing developers to add, remove, or modify middleware functions *without* impacting other parts of the system.

A common example of this is [[body-parser]] used in Node for pre-processing. Another used for logging is the [[morgan]] middleware.

## Custom Middleware

Middleware function has access to the request (req), response (res), and the `next` middleware function in the application’s request-response cycle. A custom middleware function can perform various tasks, according to our needs before ending the request-response cycle.

Suppose we have the following custom logging function:

```js
function logger(req, res, next) {
    console.log(`${req.method} ${req.url}`);
    // Call next() to pass control to the next middleware function in the stack
    next();
}
```

We can use the logger at any point of the app by simply calling `app.use(logger);`. 


> [!warning] Calling `next()`
> Remember to call `next()` to move to the next calls, otherwise the app (req,res cycle) will be stuck within the middleware call.
