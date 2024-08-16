Axios is a promise-based HTTP client for JavaScript that can be used in both browser and Node.js environments. It simplifies making HTTP requests and handling responses compared to using Node.js’s built-in http or https modules.

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
