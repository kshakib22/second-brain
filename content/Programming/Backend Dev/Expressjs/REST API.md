**REST (Representational State Transfer)** is an architectural style for designing networked applications. It relies on a stateless, client-server, cacheable communication protocol — the HTTP protocol is the most commonly used. REST APIs are used to interact with web services, allowing different systems to communicate over the internet.

**Key Principles of REST API:**

1. **Statelessness:**
   - Each request from the client to the server must contain *all the information* needed to understand and process the request.
   - The server does *not store any session information* about the client, meaning that each request is treated independently.

> [!warning] Stateless changes
> If you’re modifying a variable within a PUT request and expect the change to persist globally across your app, ensure that the variable is **globally** scoped. If it’s not, it will only be changed in the context of that particular request. If the app restarts or the variable is locally scoped, the change will be lost. To make changes persist across sessions, consider using a database.

2. **Client-Server Architecture:**
   - The client is responsible for the user interface and the server manages data and the backend.
   - This separation allows the two to evolve independently (scaling).

3. **Uniform Interface:**
   - REST APIs must adhere to a uniform interface between the client and server, which simplifies and decouples the architecture, enabling each part to evolve independently.
   - Key elements of a uniform interface include:
     - **Resource Identification**: Resources are identified using URIs.
     - **Resource Manipulation**: Resources can be manipulated through representations (e.g., JSON, XML).
     - **Self-descriptive Messages**: Each message includes enough information to describe how to process it (e.g., HTTP methods like GET, POST, PUT, DELETE).
     - **Hypermedia as the Engine of Application State (HATEOAS)**: Clients interact with the application entirely through hypermedia provided dynamically by the server.

4. **Cacheability:**
   - Responses from the server must indicate whether they are cacheable or not to prevent clients from reusing stale or inappropriate data.

5. **Layered System:**
   - The API’s architecture should be composed of layers, with each layer interacting only with its immediate layer.
   - This ensures scalability, flexibility, and the ability to handle requests through intermediaries, such as load balancers or proxies.

6. **Code on Demand (Optional):**
   - Servers can extend client functionality by transferring executable code (e.g., JavaScript) to the client. This principle is optional and not commonly used.

**Good Examples of REST API Design:**

1. **Clear and Consistent Resource Naming:**
   - Use nouns to represent resources (e.g., `/users`, `/orders`) and avoid verbs in URIs.
   - Resource names should be plural to indicate collections (e.g., `/books` for a collection of book resources).

2. **Use of HTTP Methods:**
   - **GET**: Retrieve data from a resource.
   - **POST**: Create a new resource.
   - **PUT**: Update or replace an existing resource.
   - **PATCH**: Partially update an existing resource.
   - **DELETE**: Remove a resource.

3. **Versioning:**
   - Use versioning in the URI or headers to manage API changes without disrupting existing clients (e.g., `/v1/users`).

4. **Error Handling:**
   - Use standard HTTP status codes to indicate the outcome of API requests (e.g., `200 OK`, `201 Created`, `400 Bad Request`, `404 Not Found`, `500 Internal Server Error`).
   - Provide meaningful error messages in the response body to help clients understand and resolve issues.

5. **Pagination, Filtering, and Sorting:**
   - Implement pagination for large data sets to avoid performance issues (e.g., `/users?page=2&limit=10`).
   - Allow filtering and sorting through query parameters (e.g., `/users?age=25&sort=name`).

6. **Security:**
   - Use HTTPS to encrypt communication between clients and servers.
   - Implement authentication and authorization mechanisms, such as OAuth tokens or API keys, to secure API access.

7. **Documentation:**
   - Provide clear and comprehensive documentation, including endpoint details, parameters, request/response examples, and error codes.
   - Documentation is critical for developers to understand and effectively use the API.

By adhering to these principles, REST APIs can be designed to be scalable, flexible, and easy to use, ensuring smooth communication between systems and applications.