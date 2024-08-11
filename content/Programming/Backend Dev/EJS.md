EJS stands for **Embedded JavaScript**, a templating language that lets us embed JavaScript code within our HTML. This enables dynamic content creation directly within our views. EJS is a *server-side templating engine*  that allows us to generate dynamic HTML on the server **before** sending it to the client. With EJS, we can insert data directly into our HTML templates and render the final HTML page on the server. This approach is particularly useful when the dynamic content is determined **server-side**, such as displaying user-specific data after login, rendering data from a database, or when SEO is a concern (as the full HTML is rendered and ready for search engines to crawl).

### Key Features

You can embed JavaScript logic directly within HTML using EJS syntax.

**Template Tags:**
  - `<%= %>`: Outputs the value into the HTML, and escapes it to prevent XSS attacks.
  - `<%- %>`: Outputs the unescaped value into the HTML, useful for rendering raw HTML content.
  - `<% %>`: Executes JavaScript code without producing output.

**Partial Templates:** Allows us to include and reuse code snippets across different templates. For example, we can have a header or footer template that is included on every page.

### EJS and Server-Side Rendering (SSR)

- **Server-Side Rendering:** EJS is used for rendering HTML on the server before it is sent to the client. This is crucial for dynamic web applications, as it allows the server to insert data into the HTML before it reaches the user's browser.
- **Integration with Express.js:**
  - Express provides `res.render()` to render EJS templates. This method takes the template file (without the `.ejs` extension) and an object containing the dynamic data to be passed into the template.
  - Example:
    ```javascript
    app.get('/dashboard', (req, res) => {
      res.render('dashboard', { user: req.user, title: 'User Dashboard' });
    });
    ```
  - In this example, `dashboard.ejs` is rendered with dynamic data (`user` and `title`), creating a personalized experience for the user.

## Client-Side vs. Server-Side

**Client-Side Rendering (CSR):**
  - The rendering of HTML happens on the client (in the user's browser) using JavaScript frameworks like React, Vue, or Angular.
  - Often used in single-page applications (SPAs) where the initial load fetches a minimal HTML page, and the rest of the content is rendered dynamically in the browser.

**Server-Side Rendering (SSR) with EJS:**
  - With SSR, the server sends a fully rendered HTML page to the client. EJS, when used with Express.js, is an example of SSR.
  - This can be advantageous for SEO and initial page load times since the browser receives a complete HTML page rather than waiting for JavaScript to build the content.  
  
  For example, suppose we want to create a dashboard for users after they log in. The dashboard needs to display personalized information, such as the user’s name, email, and recent activities. This data is stored on the server, and EJS allows us to render an HTML page with this data already embedded, ready to be sent to the user’s browser.

## Why Not Use `res.sendFile()` for Dynamic Content?

`res.sendFile()` is suitable for static files where the content does not change. It cannot inject dynamic data into the HTML. Example of static usage:

```javascript
app.get('/', (req, res) => {
  res.sendFile(path.join(__dirname, 'index.html'));
});
```

This sends a static `index.html` file, which is the same for every user and does not change based on server-side data.

## Practical Example: EJS in Action

`res.render()` allows for the inclusion of dynamic data directly into the HTML using EJS templates. This is essential for pages where the content needs to vary based on server-side logic, user data, or other variables.

```javascript
app.get('/profile', (req, res) => {
  res.render('profile.ejs', { user: req.user });
});
```

- First we enter the file we want to render, which is `profile.ejs`
- Next we can add a JS object to pass over some properties
 
 Here, the `profile.ejs` template is dynamically rendered with user-specific data passed in the `user` object. Here's how we could use EJS to render this dynamically:

  **views/profile.ejs:**
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><%= title %></title>
  </head>
  <body>
    <h1>Welcome, <%= user.name %>!</h1>
    <p>Your email is: <%= user.email %></p>
  </body>
  </html>
  ```