The `fs` module in Node.js provides file system-related functionality for reading from and writing to files.

**Read File** (`fs.readFile`):

• `fs.readFile("file.txt", "utf8", (err, data) => { ... })` Reads file.txt asynchronously.
	• `file.txt`: File path to read.
	• `utf8`: Encoding format for file content (optional).
	• `(err, data) => { ... }`: Callback for error handling and receiving file content.

**Write File** (`fs.writeFile`):

• `fs.writeFile("file.txt", "Hello Node!", (err) => { ... })`: Writes "Hello Node!" to file.txt.
• `file.txt`: File path to write or create.
• `"Hello Node!"`: Data to write.
• `(err) => { ... }`: Callback for error handling after write operation.