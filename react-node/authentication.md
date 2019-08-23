## install passport.js libraries
under the project dir   
install passport and strategy
```shell
npm install --save passport passport-google-oauth20
```
## import the libraries
add the require statements to index.js
```javascript
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20').Strategy;
```
## start a new google project
create a new project
enable oauth api
