# Javascript Basics
## where does javascript run
javascript can run on a browser or a node (a c++ program)
## shortcut to open the console in chrome   
```
alt + cmd + i
```
## where to put the script
best practice: at the end of the html body
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="utf-8">
    <title></title>
</head>
<body>
    <h1>Hello World</h1>
    <script type="text/javascript" src="index.js"></script>
</body>
</html>
```
## run script on node
open terminal and type
```
node filename.js
```
## a statement
a statement is an action and should be ended with a ';'
```javascript
// something like print() in python
console.log('Hello World!')
```
## variables
declare a variable
```javascript
let name = 'Ling';
// print the variable in the console
console.log(name);
// declare a variable name
// should not use the reserved keyword
// should be meaningful and descriptive
// cannot start with a number
// cannot contain space or hyphen (-)
// camel case like firstName
```
declare multiple variables   
best practice: using seperate lines
```javascript
let firstName = 'Ling';
let lastName = 'Ouyang';
```
## primitives/value types
string   
number   
boolean   
undefined   
null   
```javascript
let name = 'Ling'; // string literal
let age = 30; // number literal
let isMarried = false; // boolean literal
let lastName = undefined;
let favArtist = null; // clear the value of a variable
```
undefined can be a value and is also a type
### dynamic typing
the type of a variable can be changed

## reference types
### object
```javascript
// declare an object
let person ={
    name: 'Ling',
    age: 30
};
console.log(person);

// dot notation
person.name = 'Chris';
console.log(person.name);

// bracket notation
person[name] = 'Zhu';
console.log(person.name);
```
### array   
```javascript
// initiate an array
let selectedColors = ['red', 'blue'];
// print the first element
console.log(selectedColors[0]);
// add an element
selectedColors[2] = 'green';
// print the length of the array
console.log(selectedColors.length);
```
### function  
```javascript
// create a function
function greet(name) { // name is a parameter
    console.log('Hello ' + name);
}
// call the function
greet('Ling'); // 'Ling' is an argument
```
```javascript
function square(number) {
    return number * number;
}
// call function
let number = square(2);
console.log(number);
// or
console.log(square(2));
```
## constants
declare a constant
```javascript
const interestRate = 0.3;
```
