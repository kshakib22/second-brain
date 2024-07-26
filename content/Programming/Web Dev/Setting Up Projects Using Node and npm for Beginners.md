Node.js and npm (Node Package Manager) are essential tools for modern web development. Node.js is a runtime environment that allows you to run JavaScript on the server side, while npm is a package manager that helps you install, update, and manage JavaScript packages (libraries and tools). The following notes assume Node and npm have been installed using instructions from the official website.

## Basics

- Initialize a new npm project by creating a `package.json` file. This file keeps track of your project’s dependencies and configurations. The `-y` keeps the process short without being prompted of a lot of redundant options.

```node
npm init -y
```

*Remember* for this default flag `-y` npm always assumed the main js file is `index.js` so name it accordingly. 

- To install a package (e.g., Express for creating web servers), use the `npm install` command or `npm i`. This installs the package *locally* which means it is installed only for this project. Any install command will create a `node_modules` folder in your project directory and install all dependencies there.

- To install a package globally (available system-wide), use the -g flag:
```node
npm install -g nodemon
```

- To remove a package, use the uninstall command:
```node
npm uninstall express
```

- To update a package to the latest version, use the update command:
```node
npm update express
```

- To list all the packages installed in your project:
```node
npm list
```

## Setting up and running a Node project

- Firstly, check for `package.json`.  The presence of a `package.json` file in the root directory of the repository indicates that it’s a Node.js project. Open the `package.json` file to see the project details.

An existing project already has the required dependencies listed on `package.json` file. This means  simply install it using this command:

```node
npm install
```

- If the project needs to be built before running, look for a `build` script in `package.json` and run:
```node
npm run build
```

- Next, check for `scripts` in `package.json`. Open the `package.json` file and look for the `scripts` section. This section defines various commands to run your project. An example including `start`, `build`, `test`, etc:
```json
"scripts": {
  "start": "node index.js",
  "build": "webpack --config webpack.config.js",
  "test": "jest"
}
```

- Now we can probably run the project. The start script is already there so we can simply 
```node
npm start
```

to start running the project.