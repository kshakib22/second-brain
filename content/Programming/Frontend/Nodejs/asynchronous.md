Node.js uses an asynchronous, non-blocking model. This means operations like reading files or making network requests do not block the execution of other code. Instead, such operations are initiated, and the program continues running. When the operation completes, a callback function (or a [[promise]]) handles the result.

```js
const fs = require('fs');

// Read a file asynchronously
fs.readFile('file.txt', 'utf8', (err, data) => {
  if (err) {
    console.error(err);
    return;
  }
  console.log(data);
});

// Do something else immediately
console.log('This line does not wait for the file read to complete');
```

In this asynchronous version, `fs.readFile` starts reading the file and immediately moves to the next line. When the file read is complete, the *callback function* is invoked to handle the result. This allows the program to handle multiple tasks at once, making it more efficient.

## What would a synchronous version look like?

In synchronous JavaScript, tasks are executed one after another (single threaded approach). Each operation *waits* for the previous one to complete before moving on to the next. This can lead to blocking, where a single slow operation (like reading a file or making a network request) can hold up the entire program.

```js
const fs = require('fs');

// Read a file synchronously
const data = fs.readFileSync('file.txt', 'utf8');
console.log(data);

// Do something else
console.log('This line waits for the file read to complete');
```

In the above code, `fs.readFileSync` *blocks the execution* of the code until the file is read completely. Only after reading the file does the program move to the next line.