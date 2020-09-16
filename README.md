{
"name": "google-books-hooks",
"version": "1.0.0",
"description": "Google books API using React Hooks",
"main": "index.js",
"scripts": {
"clean": "rimraf dist",
"build:prod": "NODE_ENV=production npm run clean && webpack -p",
"start:dev": "NODE_ENV='development' webpack-dev-server",
"test": "echo \"Error: no test specified\" && exit 1"
},
"keywords": [
"hooks",
"react"
],
"author": "Ricky Liew",
"license": "ISC",
"devDependencies": {
"@babel/core": "^7.11.6",
"@babel/preset-env": "^7.11.5",
"@babel/preset-react": "^7.10.4",
"babel-loader": "^8.1.0",
"css-loader": "^4.3.0",
"dotenv": "^8.2.0",
"eslint": "^7.8.1",
"eslint-plugin-react": "^7.20.6",
"html-webpack-plugin": "^4.4.1",
"rimraf": "^3.0.2",
"style-loader": "^1.2.1",
"webpack": "^4.44.1",
"webpack-cli": "^3.3.12",
"webpack-dev-server": "^3.11.0"
},
"dependencies": {
"axios": "^0.20.0",
"react": "^16.13.1",
"react-dom": "^16.13.1",
"react-hot-loader": "^4.12.21"
}
}
