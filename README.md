# Express Generated Project to Typescript

## Generate express project
* `npx express-generator <dir name>`. To create express project with name.
* `npm install` and `npm start` to start server at port 3000.

## Converting to typescript
* `npm install --save-dev typescript @types/cookie-parser @types/http-errors @types/morgan @types/node ts-node`. Installs necessary dependencies in types for express.
* `npx tsc --init` to create tsconfig file.
* create a `src` folder and move `/routes` and `app.js` into it. Delete `/views` since we dont need it.
>Note: since we ignoring the views, change `res.render` to `res.send("text")`
* Change the tsconfig's configs.
* Rename all the extensions in `/src` from `.js` to `.ts`.
* Once renamed, change all imports from `require` to `import` syntax.
* Since app.js is repositioned, in `bin/www` file change 
```diff
- var app = require('../app');
+ var app = require('../dist/app');
```

## Starting server
* `npm start` will start server at port 3000.
>Note: will just compile the .ts files and starts the server. **DOES NOT WATCH FOR FILE CHANGES** 

## Debugging typescript
* Create a `.vscode/launch.json` file if working with vsc and copy below content. [More info](https://code.visualstudio.com/docs/typescript/typescript-debugging)
* Intentionally `/.vscode` folder was not git ignore. can see launch.json
* Add a debugger point in the file and press `f5` to start server in debugger mode.
