Middleware in web development generally refers to **middleware functions** that acts as a **bridge** between database and applications, especially on a network. It is a key part of backend development, handling various tasks between the client and the server.

- **Request and Response Handling**: Middleware functions typically handle HTTP requests and responses, processing them *before* they reach the server’s core logic or before the responses are sent back to the client.
- **Pre-Processing**: Middleware can perform operations such as logging, authentication, and session management, transforming the request object before it reaches the main application logic.
- **Post-Processing**: Middleware can also modify the response object before sending it back to the client, for example, formatting data, adding headers, or compressing responses.
- **Authentication**: Verify whether request is allowed before we process them.

Middleware functions are executed sequentially in the *order they are defined* in the application. Each middleware function **must** either:
- Call `next()` to pass control to the next middleware function.
- End the request-response cycle (e.g., by sending a response).


> [!NOTE] Acessing `req, res, next()`
> When we define a middleware function in Express, it *automatically* gets the `req`, `res`, and `next` parameters from the Express framework.

**Benefits:** By introducing a middleware, we allow for *separation of concerns*, making the codebase more modular and maintainable. Middleware functions can be reused across different parts of the application or even in different projects. This also facilitates scaling by allowing developers to add, remove, or modify middleware functions *without* impacting other parts of the system.

A common example of this is [[body-parser]] used in Node for pre-processing. Another used for logging is the [[morgan]] middleware.