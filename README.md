## Initial Setup

Followed https://www.freecodecamp.org/news/how-to-enable-es6-and-beyond-syntax-with-node-and-express-68d3e11fe1ab/

Repo is here

Skipped steps for converting existing scripts to es6

1. npx express-generator your-project-name --no-view
1. cd your-project-name
1. create a server/ folder
1. Put bin/ , app.js , and routes/ inside the server/ folder.
1. Rename www, found in bin to www.js
1. Leave public/ folder at your project root.
1. npm install --save npm-run-all
1. npm install --save @babel/core @babel/cli @babel/preset-env nodemon rimraf
1. npm install --save-dev jest
1. Created car.js and called it from app.js to prove es6 classes work
1. Changed package.json
    ```
    "scripts": {
    "start": "npm run prod"
    "build": "npm-run-all clean transpile"
    "server": "node ./dist-server/bin/www",
    "dev": "NODE_ENV=development npm-run-all build server",
    "prod": "NODE_ENV=production npm-run-all build server",
    "transpile": "babel ./server --out-dir dist-server",
    "clean": "rimraf dist-server".
    "watch:dev": "nodemon", 
    "test": "jest" 
    },
    "nodemonConfig": {
    "exec": "npm run dev",
    "watch": [ "server/*", "public/*" ],
    "ignore": [ "**/__tests__/**", "*.test.js", "*.spec.js" ] 
    }, 
    "babel": { 
    "presets": [ "@babel/preset-env" ]
    },
    "jest": {
    "testEnvironment": "node"
    }
    ```

