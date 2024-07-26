Earlier JS could only be used for websites/web-apps until Node.js changed that. Node.js is a [runtime](../Runtime.md) that allows you to run JavaScript code outside of a web browser. Built on the [[V8 engine]], Node.js is designed for building scalable network apps.

It uses an [[asynchronous]], event-driven, non-blocking I/O model, which makes it lightweight and efficient. This is especially useful for real-time applications like chat servers, APIs, and streaming services. Node.js also comes with npm (Node Package Manager), which provides thousands of libraries and tools for developers to enhance their applications.

## Native Modules

Native Node modules, also known as core modules, are built into Node.js. They provide essential functionalities without requiring any additional installation. These modules are written in JavaScript or C++. Some common ones are listed below -

1. **fs** **([[File System]]):**
	• Used for file operations like reading, writing, and manipulating the file system.
2. **http** and **https**
3. **path**
	• Utilities for working with file and directory paths
4. **os**
	• Provides operating system-related utility methods and properties
5. **events**
	• Implements the EventEmitter class, used for handling events and asynchronous functions.

```js
const fs = require('fs');
const http = require('http');
const path = require('path');
// os usage
const os = require('os');
console.log(os.platform());

// event usage
const EventEmitter = require('events');
const myEmitter = new EventEmitter();
myEmitter.on('event', () => {
  console.log('An event occurred!');
});
myEmitter.emit('event');
```

For simplifying our experience with Node, we will learn building backend/server using Express.js framework. Express is started from [Intro to Express js](../Expressjs/0-Intro.md). To review how basic node and npm packages work for beginners in setting up projects, look at [Setting Up Projects Using Node and npm for Beginners](../Setting%20Up%20Projects%20Using%20Node%20and%20npm%20for%20Beginners.md). 