Here is an overview of how a Node/JS project involving EJS would arrange its files. Main point to remember - `/views` contains the `.ejs` files (equivalent to HTML) and `/public` contains other static files such as css, images etc.

```python
/project-root
│
├── /node_modules    # Directory for installed npm packages
│
├── /public          # Publicly accessible files (CSS, JavaScript, images)
│   ├── /css         # CSS files
│   ├── /js          # Client-side JavaScript files
│   ├── /images      # Images
│   └── /assets      # Other assets (fonts, etc.)
│
├── /views           # EJS templates
│   ├── /partials    # Reusable EJS partials (headers, footers, etc.)
│   └── index.ejs    # Main EJS template (example)
│
├── /routes          # Route definitions
│   └── index.js     # Main route file
│
├── /controllers     # Logic for handling requests
│   └── indexController.js   # Example controller
│
├── /middlewares     # Custom middleware functions
│   └── auth.js      # Authentication middleware (example)
│
├── /config          # Configuration files (database, environment, etc.)
│   └── db.js        # Database configuration (example)
│
├── /models          # Database models (if using a database)
│   └── user.js      # Example model
│
├── /utils           # Utility functions/helpers
│   └── helpers.js   # Example utility file
│
├── /test            # Test files
│   └── test.js      # Example test file
│
├── .env             # Environment variables (ignored in version control)
├── .gitignore       # Files and directories to ignore in version control
├── package.json     # Project metadata and dependencies
├── package-lock.json # Exact versions of installed dependencies
├── app.js           # Main application file
└── README.md        # Project documentation

```

- /node_modules: Contains all the npm packages installed for the project.
- /public: Houses all the static files (CSS, JavaScript, images, etc.) that are served directly to the client.
-	/views: Contains all the EJS templates. The partials directory stores reusable components like headers, footers, and navigation bars.
- /routes: Defines the application’s endpoints and maps them to controller functions.
-  /controllers: Handles the logic for each route, processing requests, and returning responses.
- /middlewares: Stores custom middleware functions that process requests before they reach the routes.
- /config: Configuration files for database connections, environment variables, and other settings.
- /models: If using a database, this directory contains the schema definitions and models.
- /utils: Utility functions or helper methods used throughout the application.
- /test: Test files for the application, often written with a testing framework.
- app.js: The main entry point of the application, where the Express app is configured and started.

## Connecting different parts

- The `app.use(express.static("public"))` line in an Express.js application serves static files like images, CSS, JavaScript, etc., from the public directory.