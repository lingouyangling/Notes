# local machine
## set up a new project
make a new dir
```
mkdir server
```
go to the dir
```
cd server
```
## express
initiate npm
```shell
npm init
```
go through the set up and a package.json file is generated
```shell
npm install --save express
```
express is now installed, check the json file
```
cat package.json
```
## create server application
create a new file index.js under the project dir
```javascript
const express = require('express'); //import the express library
const app = express(); //create an express application

/*
app: a route handler
get() function: watch for incoming get-method requests
'/': watch for requests trying to access the root route '/'
req: incoming request
res: outgoing response
*/
app.get('/', (req, res) => {
    res.send({hello: 'world'});
});

const PORT = 5000;

app.listen(PORT); //tell node server to listen to the port
```
## serve up
terminal
```
node index.js
```
open localhost:5000 in browser and check
# pre-deploy configurations
## dynamic port binding
cloud service provider will assign a port to node, and the port is in the environment variables, change the index.js to
```javascript
const express = require('express'); //import the express library
const app = express(); //create an express application

/*
app: a route handler
get() function: watch for incoming get-method requests
'/': watch for requests trying to access the root route '/'
req: incoming request
res: outgoing response
*/
app.get('/', (req, res) => {
    res.send({hello: 'world'});
});

const PORT = process.env.PORT || 5000; /* find port from the environment variables assigned by the cloud provider,
if run on local machine, there's no port in the environment variables, use 5000 instead*/

app.listen(PORT); //tell node.js to listen to the port
```
## specify node environment
specify node version and npm version in by adding the following object to package.json
```json
"engines": {
  "node": "8.1.1",
  "npm": "5.0.3"
}
```
## specify start script
replace the "script" object in package.json with
```json
"script": {
  "start": "node index.js"
}
```
## create .gitignore file
To not commit dependency folder, which was downloaded when installing express, to git, create a new .gitignore file under project dir and add the dependency folder name to the file
```
node_modules
```
# first-time deploy
## create Heroku account
## commit codebase to git
under the project dir
```shell
git init
```
```shell
git add .
```
```shell
git commit -m "initial commit"
```
## install Heroku CLI and create app
### install Heroku CLI
```shell
brew tap heroku/brew && brew install heroku
```
check installation
```shell
heroku -v
```
### create new app
```shell
heroku login
```
```shell
heroku create
```
heroku will return a url of the app and a url of the git remote repo
## deploy app with git
```shell
git remote add heroku <remote repo url>
```
push codebase to heroku
```shell
git push heroku master
```
check the app in browser
```shell
heroku open
```
show logs for debugging
```shell
heroku logs
```
# subsequent deploy
some changes have been made
```shell
git add .
```
```shell
git commit -m "some changes"
```
```shell
git push heroku master
```
