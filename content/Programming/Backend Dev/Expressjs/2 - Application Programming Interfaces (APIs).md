
The main point of an API in terms of backend and software is to allow different systems or components to communicate and work together. In the backend, an API provides a way for different parts of an application (like the server, database, and client-side) to interact efficiently. It enables software systems to request data, perform operations, and receive results without needing to understand the underlying complexity of each other. 

Data being transferred is usually in the [JSON](../JSON.md) format. Key things to remember - 
 - `JSON.parse()`: Converts a JSON string into a JavaScript object.
  - `JSON.stringify()`: Converts a JavaScript object into a JSON string.
  - Members of an object can be accessed using both dot operator (fixed) and square brackes - `["memberName"]` (variables can be used)

The minimum basics of API requests using the URL of the API can be reviewed at [[Structuring API requests]].

Similar to how Express simplified Node code to deal with route handling, middleware and req, res, **Axios** is a similar framework for APIs. Check out the detailed notes on [Axios](Axios.md). Learning the complete basics of Axios is *essential* before moving to further parts because that is our framework of choice for further API stuff such as authentication and transfer of data.


> [!warning] Mutiple `app.post` requests
> Review [HTML forms](../../Web%20Dev/HTML/HTML%20forms.md) to understand why all post, put, patch and sometimes even get requests also use `app.post` method

## Common Use of Variables
- **`req.body`**: Often used in `POST` requests to access data sent from the client, such as **form data**.
- **`req.query`**: Used in `GET` requests to access query parameters appended to the URL.
- **`req.params`**: Used to access parameters defined in the route path, such as `/user/:id`.
  
## Order of Parameters in Axios Requests

**In `POST` requests**:
  - **First Parameter**: The *URL* (e.g., `API_URL + "/secrets"`).
  - **Second Parameter**: The *data* (e.g., `req.body` or an object containing data).
  - **Third Parameter**: The config object (e.g., Bearer token authentication, headers, query parameters, etc.).
  
```javascript
const response = await axios.post(API_URL + "/secrets", req.body, customConfig);
```

 **In `GET` requests**:
  - **First Parameter**: The URL (e.g., `API_URL + "/secrets"`).
  - **Second Parameter**: The config object (optional, used for query parameters, headers, etc.).
  
  ```javascript
  const response = await axios.get(API_URL + "/secrets", customConfig);
  ```
