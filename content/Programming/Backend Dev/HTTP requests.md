
1. **GET** : Retrieve data from a server.
-  Read-only.
-  No effect on server data.
-  Can be cached.
-  Can be bookmarked.
-  Parameters are included in the URL.

2. **POST** : Submit data to a server to create a resource.
-  Used for form submissions.
-  Data included in the body of the request.
-  Not idempotent (multiple requests can create multiple resources).
-  Can upload files.

3. **PUT** : Update or create a resource on the server.
-  Idempotent (multiple requests result in the same state).
-  Replaces the entire resource.
-  Data included in the body of the request.

4. **PATCH** : Apply partial modifications to a resource.
-  Not necessarily idempotent.
-  Updates part of the resource.
-  More efficient for partial updates than PUT.

5. **DELETE** : Remove a resource from the server.
-  Idempotent (multiple requests have the same effect).
-  Can delete resources.
-  Rarely has a body in the request.