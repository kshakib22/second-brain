
EJS Partials allow developers to reuse common sections of HTML code across multiple views, making the codebase more maintainable and DRY (Don’t Repeat Yourself). They are typically used for sections like headers, footers, navigation bars, or any other part of the HTML that repeats across multiple pages.

- Partials are created as separate EJS files, typically stored in a partials directory.
- They are included in other EJS files using the <%- include('path_to_partial') %> syntax.

Example Structure:
- /views
	- /partials
	- header.ejs
	- footer.ejs

Suppose our header and footer are as follows: 

```html
<!-- header.ejs -->
<header>
  <h1>My Website</h1>
  <nav>
    <a href="/">Home</a>
    <a href="/about">About</a>
    <a href="/contact">Contact</a>
  </nav>
</header>
```

```html
<!-- footer.ejs -->
<footer>
  <p>&copy; 2024 My Website</p>
</footer>
```

Then we can include in our main ejs file `index.ejs` using templating as such -

```html
<!-- index.ejs -->
<%- include('partials/header') %>
<main>
  <h2>Welcome to the Home Page</h2>
  <p>This is the main content area.</p>
</main>
<%- include('partials/footer') %>
```
