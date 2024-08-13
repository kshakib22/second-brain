EJS stands for **Embedded JavaScript**, a templating language that lets us embed JavaScript code within our HTML. This enables dynamic content creation directly within our views. EJS is a *server-side templating engine*  that allows us to generate dynamic HTML on the server **before** sending it to the client. With EJS, we can insert data directly into our HTML templates and render the final HTML page on the server. This approach is particularly useful when the dynamic content is determined **server-side**, such as displaying user-specific data after login, rendering data from a database, or when SEO is a concern (as the full HTML is rendered and ready for search engines to crawl).

### Key Features

You can embed JavaScript logic directly within HTML using EJS syntax.

| EJS Tag Type                       | Syntax             | Function                                                             |
| ---------------------------------- | ------------------ | -------------------------------------------------------------------- |
| Output Tag                         | `<%= %>`           | Embeds and outputs the value of an expression into HTML.             |
| Unescaped Output Tag (Render HTML) | `<%- %>`           | Outputs the value of an expression without escaping HTML characters. |
| Scriptlet Tag (only JS code)       | `<% %>`            | Executes JavaScript code without outputting anything to the HTML.    |
| Comment Tag                        | `<%# %>`           | Adds comments that won't appear in the rendered HTML.                |
| Include Tag                        | `<%- include() %>` | Embeds another EJS template or partial into the current template.    |


> [!NOTE] EJS files
> EJS files typically looks like a typical HTML file, with EJS code in different parts of it

### EJS and Server-Side Rendering (SSR)

- **Server-Side Rendering:** EJS is used for rendering HTML on the server before it is sent to the client. This is crucial for dynamic web applications, as it allows the server to insert data into the HTML before it reaches the user's browser.
- **Integration with Express.js:**
  - Express provides `res.render()` to render EJS templates. This method takes the template file (without the `.ejs` extension) and an object containing the dynamic data to be passed into the template.
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

## Locals

In EJS `locals` are basically **all** the variables passed from the server to an EJS template. 
- Locals variable *always* exist. We access variables passed using for example `locals.varName`
- We can check using locals whether certain data exists, because EJS doesn't check it by default
- locals make it easy to handle cases where some data might be *optional or conditional*.
- This is especially useful in complex views where different parts of the page need to be shown or hidden based on the availability of data.  

> [!warning] Empty locals
> If we call   `res.render("index.ejs");` without passing any data, `locals` will *always* be empty

The following example shows a typical use of locals to ensure a certain variable (`username` in this case) has been passed to the server properly. In case it doesn't exist, we show something else in the HTML.

```js
const express = require('express');
const app = express();

app.get('/profile', function(req, res) {
    // Simulating a situation where 'username' might or might not be present
    const user = req.query.user ? { username: req.query.user } : {};
    
    // Passing user object to the EJS template
    res.render('profile', user);
});

app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profile Page</title>
</head>
<body>
    <% if (locals.username) { %>
        <h1>Welcome, <%= locals.username %>!</h1>
    <% } else { %>
        <h1>Welcome, Guest!</h1>
    <% } %>
</body>
</html>
```




## User Data to Server

What about the other direction when we want dynamic data from the user into our server logic? This will usually involve a POST method and a way to receive that data from HTML using a form, for example. The form data is sent as part of the HTTP request, typically through `req.body` for POST requests. Consider the following HTML where two variables are `username` and `password` : 

```html
<form action="/submit" method="POST">
  <input type="text" name="username" placeholder="Enter your username">
  <input type="password" name="password" placeholder="Enter your password">
  <button type="submit">Submit</button>
</form>
```

These can be sent through the javascript app code (considering password was correct, also checked in the app):
```js
app.post('/submit', function(req, res) {
  const username = req.body.username;
  res.render('welcome', { username: username });
});
```