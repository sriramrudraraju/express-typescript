# Express Generated Project to Typescript

## Generate express project
* `npx express-generator <dir name>`. To create express project with name.
* `npm install` and `npm start` to start server at port 3000.

## Converting to typescript
* `npm install --save-dev typescript @types/cookie-parser @types/http-errors @types/morgan @types/node ts-node`. Installs necessary dependencies in types for express.
* `npx tsc --init` to create tsconfig file.
* create a `src` folder and move `/routes` and `app.js` into it. Delete `/views` since we dont need it.
>Note: since we ignoring the views, change `res.render` to `res.send("hello world")` in `/routes/index.ts`
* Change the tsconfig's configs.
* Rename all the extensions in `/src` from `.js` to `.ts`.
* Once renamed, change all imports from `require` to `import` syntax.
* Since app.js is repositioned, in `bin/www` file change 
```diff
- var app = require('../app');
+ var app = require('../dist/app');
```