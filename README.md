{
"name": "x_gbooks2",
"version": "1.0.0",
"description": "## Contents",
"main": "index.js",
"scripts": {
"clean": "rimraf dist",
"build:prod": "NODE_ENV=production npm run clean && webpack -p",
"build:dev": "NODE_ENV=development npm run clean && webpack -p",
"serve:dev": "NODE_ENV=development webpack-dev-server --watch"
},
"author": "",
"license": "ISC",
"devDependencies": {
"@babel/core": "^7.11.6",
"@babel/preset-env": "^7.11.5",
"@babel/preset-react": "^7.10.4",
"babel-loader": "^8.1.0",
"css-loader": "^4.3.0",
"dotenv": "^8.2.0",
"eslint": "^7.10.0",
"eslint-plugin-react": "^7.21.2",
"html-webpack-plugin": "^4.5.0",
"mini-css-extract-plugin": "^0.11.2",
"rimraf": "^3.0.2",
"webpack": "^4.44.1",
"webpack-cli": "^3.3.12",
"webpack-dev-server": "^3.11.0"
},
"dependencies": {
"react": "^16.13.1",
"react-dom": "^16.13.1",
"react-hot-loader": "^4.13.0"
}
}
