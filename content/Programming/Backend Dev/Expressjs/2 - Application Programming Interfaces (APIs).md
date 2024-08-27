
The main point of an API in terms of backend and software is to allow different systems or components to communicate and work together. In the backend, an API provides a way for different parts of an application (like the server, database, and client-side) to interact efficiently. It enables software systems to request data, perform operations, and receive results without needing to understand the underlying complexity of each other. 

Data being transferred is usually in the [JSON](../JSON.md) format. Key things to remember - 
 - `JSON.parse()`: Converts a JSON string into a JavaScript object.
  - `JSON.stringify()`: Converts a JavaScript object into a JSON string.
  - Members of an object can be accessed using both dot operator (fixed) and square brackes - `["memberName"]` (variables can be used)

The minimum basics of API requests using the URL of the API can be reviewed at [[Structuring API requests]].

Similar to how Express simplified Node code to deal with route handling, middleware and req, res, **Axios** is a similar framework for APIs. Check out the detailed notes on [Axios](Axios.md). Learning the complete basics of Axios is *essential* before moving to further parts because that is our framework of choice for further API stuff such as authentication and transfer of data.

