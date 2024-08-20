
The main point of an API in terms of backend and software is to allow different systems or components to communicate and work together. In the backend, an API provides a way for different parts of an application (like the server, database, and client-side) to interact efficiently. It enables software systems to request data, perform operations, and receive results without needing to understand the underlying complexity of each other. 

Data being transferred is usually in the [JSON](../JSON.md) format. Key things to remember - 
 - `JSON.parse()`: Converts a JSON string into a JavaScript object.
  - `JSON.stringify()`: Converts a JavaScript object into a JSON string.
  - Members of an object can be accessed using both dot operator (fixed) and square brackes - `["memberName"]` (variables can be used)

Similar to how Express simplified Node code to deal with route handling, middleware and req, res, **Axios** is a similar framework for APIs. Check out the detailed notes on [Axios](Axios.md). 

## Structuring API requests

### Path Parameters

- Used to identify a specific resource or resource instance.
- Integral to the URL path, making them part of the endpoint.

**Usage:**
- **Syntax:** `/resource/{parameter}/subresource/{subparameter}`
- **Example:** `/users/123` where `123` is a path parameter identifying a user.

**Characteristics:**
- Typically used for resource identification and hierarchy.
- Essential to the API's endpoint structure.
- Generally static and fixed.

**Code Example (Express.js):**
```javascript
app.get('/users/:userId', (req, res) => {
    const userId = req.params.userId;
    // Fetch user by userId
    res.send(`User ID: ${userId}`);
});
```


### Query Parameters

- Used to filter, sort, or modify the request’s scope or behavior.
- Optional and appended to the URL after the question mark ?.

- Syntax: /resource?param1=value1&param2=value2
- Example: /products?category=electronics&priceRange=100-500 where category and priceRange are query parameters.

Characteristics:
- Typically used for searching, filtering, and pagination.
- Flexible and can be combined in various ways.
- Not part of the endpoint structure but appended to the URL.

```js
app.get('/products', (req, res) => {
    const category = req.query.category;
    const priceRange = req.query.priceRange;
    // Fetch products based on category and priceRange
    res.send(`Category: ${category}, Price Range: ${priceRange}`);
});
```
