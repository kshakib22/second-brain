Body-parser is a middleware for Node.js used to parse incoming request bodies in a middleware before any handlers. This make the **req.bod**y property available to use. Most commonly this is used to handle different **form** data.

Body-parser has been deprecated in Express 4.16.0+ as most of its functionality is now included in Express. The `express.json()`and `express.urlencoded()` methods are direct replacements.

```node
// To parse URL-encoded payloads
app.use(bodyParser.urlencoded({ extended: true }));

// or use the one available with express
app.use(express.urlencoded({ extended: true }));
```