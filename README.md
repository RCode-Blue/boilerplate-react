# JavaScript from Scratch

## Contents
[Part 1: Basics](#part-1-basics)
- [Phase 1: Use this template](#phase-1-use-this-template)
- [Phase 2: Basic Installs](#phase-2-basic-installs)
  
[Part 2: React from Scratch](#part-2-react-from-scratch)
- [Phase 1: Configure Webpack](#phase-1-configure-webpack)
- [Phase 2: Set up React](#phase-2-set-up-react)
- [Phase 3: Configure Styling & Images](#phase-3-configure-styling-and-images)

[Part 3: Express from Scratch](#part-3-express-from-scratch)



[References](#references)

<br/><br/><br/>


# Part 1: Basics
## Phase 1: Use this template
1. It has config files for Editor Config, ESLint and Prettier
2. Install install the eslint plugin 
 
```
npm install –save eslint
npm install eslint-plugin-react –save-dev 
```

3. Add the following in the `.eslintrc` file: 

```json
{ 
"extends": ["eslint: recommended", "plugin:react/recommend"] 
} 
```
More details [here](https://github.com/yannickcr/eslint-plugin-react#recommended). 


## Phase 2: Basic Installs

1. Initialise NPM

```
npm init
```
Answer all questions, or use `npm init --y` to take all defaults


2. Install Webpack and Babel

```
npm install --save-dev rimraf webpack webpack-dev-server @babel/core babel-loader @babel/preset-env
```

create `webpack.config.js` at project root

Add the following to `package.json`:

```json
"scripts": { 
  "build": "webpack" 
} 
```

3. Create files

Folder structure:
```
<project_root>
|-- .babelrc
|-- package.json
|-- webpack.config.js

```

# Part 2: React from Scratch

## Phase 1: Configure Webpack

`.babelrc:`
```json
{
  "presets": ["@babel/preset-env"]
}
```

`webpack.config.js:`
```js
const path = require("path");

module.exports = {
  entry: {
    bundle: "./src/index.js"
  }
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "bundle.js",
    publicPath: "dist/"
  },
  module: {
    rules[
      {
      use: "babel-loader",
      test: /\.js$/
      }
    ]
  }
}

module.exports = config;
```


## Phase 2: Set up React


1. Install React

```
npm install react
```

2. Create files

Folder structure:
```
<project_root>
|-- .babelrc
|-- package.json
|-- webpack.config.js
|-- src
    |-- index.html
    |-- index.js
```

3. Setup basic React

`src/index.html:`:

```html
<!DOCTYPE html>
  <head></head>
  <body> 
    <div id="root">n</div>
    <script src="bundle.js"></script>
  </body> 
</html>
```

`src/index.js:`
```js
import React from "react";
import ReactDOM from "react-dom";

ReactDOM.render(
  document.getElementById("root")
);
```
   
4. Setup NPM run scripts

`package.json:`
```json
...
"scripts" {
  "clean": "rimraf",
  "build": "NODE_ENV=production npm run clean && webpack -p",
  "clean": "rimraf dist",
  "dev": "webpack-dev-server"
}
```

## Phase 3: Configure Styling and Images
*(optional. skip if creating backend APIs)*

1. Setup CSS

```
npm install –save-dev css-loader mini-css-extract-plugin
```
`webpack.config.js:`
```js
const MiniCssExtractPlugin = require("mini-css-extract-plugin"); 

plugins: [new MiniCssExtractPlugin()], 
rules: [{ 
  use: [
    MiniCssExtractPlugin.loader, 
    'css-loader'
  ], 
  test: /\.css$/ 
}] 
```

2. Setup SASS

```
npm install –save-dev  node-sass sass-loader 
```
 
`webpack.config.js:`: 

```js
rules: [ 
  { 
    test: /\.s[ac]ss$/i, 
    use: [ 
      // Creates `style` nodes from JS strings 
      'style-loader', 

      // Compiles Sass to CSS 
      'sass-loader', 
    ], 
  }, 
```

1. Configure Images

```
npm install --save-dev image-webpack-loader url-loader 
```
 

`webpack.config.js:`: 
```js
rules: [
  test: /\.(jpe?g|png|gif|svg)$/, 
  use: [ 
  {
  'url-loader', 
  options: { limit: 40000 } 
  }, 
  'image-webpack-loader' 
  ] 
] 
```

# Part 3: Express from Scratch
## Phase 1: Basic Express Server Setup

1. Install `Express:`
```
npm install --save express
```

2. Create files

Folder structure:
```
<project_root>
|-- .babelrc
|-- package.json
|-- webpack.config.js
|-- src
    |-- server.js
    |-- index.html
```

3. Setup `NPM` run scripts

`package.json:`
```json
"scripts":{
  "start": "node ./server.js"
}
```

4. Create basic Express server files

`server.js:`
```js
const path = require("path");
const express = require ("express");

const app = express(),
  DIST_DIR = __dirname,
  HTML_FILE = path.join(DIST_DIR, "index.html");

app.get("*", (req, res) => {
  res.sendFile(HTML_FILE)
})

const PORT = process.env.PORT || 8080
app.listen(PORT, () => {
  console.log(`Listening on port ${PORT}...`);
  console.log("Press Ctrl+C to quit.");
})
```

`index.html:`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>Express and Webpack Boilerplate</title>
    <link rel="shortcut icon" href="#">
</head>
<body>
    <p class="description">Express and Webpack Boilerplate App</p>
</body>
</html>
```

5. Test and run
```
npm start
```
Browse to `http://localhost:8080`

## Phase 2: Configure Webpack



<br/><br/><br/>
## References

### React:
[Step-By-Step: Create a React Project from Scratch](https://www.codementor.io/@rajjeet/step-by-step-create-a-react-project-from-scratch-11s9skvnxv)

### Express:
[Creating a Node Express-Webpack App with Dev and Prod Builds](https://medium.com/@binyamin/creating-a-node-express-webpack-app-with-dev-and-prod-builds-a4962ce51334)
