Axios is a promise-based HTTP client for JavaScript that can be used in both browser and Node.js environments. It simplifies making HTTP requests and handling responses compared to using Node.js’s built-in http or https modules.

## Motivation
Let's see an example that uses `http` module from Node to deal with requests:

```node
const http = require('http');

const options = {
  hostname: 'jsonplaceholder.typicode.com',
  path: '/todos/1',
  method: 'GET',
  headers: { 'Content-Type': 'application/json' },
};

const req = http.request(options, (res) => {
  let data = '';

  res.on('data', (chunk) => {
    data += chunk;
  });

  res.on('end', () => {
    console.log(JSON.parse(data));
  });
});

req.on('error', (e) => {
  console.error(`Problem with request: ${e.message}`);
});

req.end();
```

- deals with options separately with request type, URL, etc
- data needs to be processed from being packets/chunks to a single string
- json-ify the string and then pass the data

Compare this to Axios :

```js
const axios = require('axios');

axios.get('https://jsonplaceholder.typicode.com/todos/1')
  .then(response => {
    console.log(response.data);
  })
  .catch(error => {
    console.error(`Error: ${error.message}`);
  });
```

- simple get request to URL
- direct response (without processing) as JSON
- easier error handling (no need to deal with individual status codes)

### Comparison: `.then()` Chaining vs. `async/await`

This is the traditional way of handling promises in JavaScript, where the `then()` method is chained to handle resolved values or errors.
```javascript
axios.get('https://api.example.com/data')
.then(response => {
  console.log(response.data);
})
.catch(error => {
  console.error('Error:', error.message);
});
```

But we will use `async/await` for a cleaner, more readable syntax for handling promises, making it easier to write and understand asynchronous code.

```js
const fetchData = async () => {
  try {
    const response = await axios.get('https://api.example.com/data');
    console.log(response.data);
  } catch (error) {
    console.error('Error:', error.message);
  }
};

fetchData();
```

## Important terms

In backend development, many operations, such as reading files, interacting with databases, or making HTTP requests, are asynchronous. Promises, async, and await help manage these operations without blocking the execution of other code.

1. **Promise**: A Promise in JavaScript represents an operation that will complete in the future, either successfully (resolved) or unsuccessfully (rejected).
	- Promises simplify working with asynchronous operations, such as fetching data from an API, by allowing us to handle success and failure in a structured way.
2. **async**: A keyword used to define an asynchronous function. When a function is marked as async, it automatically returns a promise.
3. **await**: A keyword used inside *async functions* to pause the execution until the promise is resolved. It allows us to write asynchronous code that looks and behaves more like synchronous code.
	- async/await makes the code easier to read and understand by avoiding the need for complex `.then()` chains.
	- try...catch blocks can be used to handle errors when using async/await, making the code cleaner.
	- `await` pauses execution of only the portion **inside the `async` function**. The rest of the program keeps running (following the original `async` concept)

```javascript
async function fetchData() {
  try {
	const response = await axios.get('https://api.example.com/data');
	console.log(response.data);
  } catch (error) {
	console.error('Error fetching data:', error);
  }
}
fetchData();
```


## Basics of Axios

**Sending GET Requests**
  - Use `axios.get(url)` to retrieve data from a server.
```javascript
const express = require('express');
const axios = require('axios');

const app = express();

app.get('/data', async (req, res) => {
  try {
    const response = await axios.get('https://api.example.com/data');
    res.json(response.data);
  } catch (error) {
    res.status(500).json({ error: 'Failed to fetch data' });
  }
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

 **Sending POST Requests**
  - Use `axios.post(url, data)` to send data to a server.
```javascript
app.post('/send', async (req, res) => {
  try {
    const response = await axios.post('https://api.example.com/data', req.body);
    res.json(response.data);
  } catch (error) {
    res.status(500).json({ error: 'Failed to send data' });
  }
});
```

**Handling Errors**
  - Errors are handled in the `.catch` method.
```javascript
app.get('/error-example', async (req, res) => {
  try {
    const response = await axios.get('https://api.example.com/nonexistent');
    res.json(response.data);
  } catch (error) {
    res.status(500).json({ error: error.message || 'An error occurred' });
  }
});
```


## Sending data through Axios

- **`params`**:
  - Used to specify URL query parameters in `GET` requests.
  - Converts object properties into query string parameters.
   
    ```javascript
    axios.get('/endpoint', { params: { id: 123 } });
    // Results in: /endpoint?id=123
    ```

- **`data`**:
  - Used to send data in the body of `POST`, `PUT`, `PATCH`, or `DELETE` requests.
  - Accepts an object or a string.
   
    ```javascript
    axios.post('/endpoint', { data: { name: 'John' } });
    ```

- **`headers`**:
  - Used to set custom HTTP headers for a request.
  - Can be used to set authorization tokens, content types, etc.
   
    ```javascript
    axios.get('/endpoint', {
      headers: { Authorization: `Bearer ${token}` }
    });
    ```

- **`auth`**:
  - Provides a shortcut to send *basic authentication* headers.
  - Takes an object with `username` and `password`.
   
    ```javascript
    axios.get('/endpoint', {
      auth: { username: 'user', password: 'pass' }
    });
    ```

- **`timeout`**:
  - Sets the number of milliseconds before the request times out.
  - If the request takes longer than the specified time, it will be aborted.
   
    ```javascript
    axios.get('/endpoint', { timeout: 5000 }); // 5 seconds
    ```

- **`responseType`**:
  - Defines the type of data expected in the response.
  - Common values: `'json'`, `'blob'`, `'document'`, `'text'`, `'stream'`.
   
    ```javascript
    axios.get('/file', { responseType: 'blob' });
    ```

- **`baseURL`**:
  - Sets a base URL for all requests made using the instance.
  - All relative URLs will be prepended with this base URL.

    ```javascript
    const instance = axios.create({ baseURL: 'https://api.example.com' });
    instance.get('/users'); // Request to https://api.example.com/users
    ```

- **`method`**:
  - Specifies the HTTP method to be used (e.g., `GET`, `POST`, `PUT`, `DELETE`).
   
    ```javascript
    axios({
      method: 'post',
      url: '/endpoint',
      data: { name: 'John' }
    });
    ```

Check [[Axios authentication types]] for different authentications and how exactly to deal with them.