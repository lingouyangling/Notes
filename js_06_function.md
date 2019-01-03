## declarations vs expressions
```javascript
// function declaration, can be defined after calling
function walk() {
    console.log('walk');
}

// function expression, cannot be called definination
let run = function() {
    console.log('run');
};

// call function
run();

// reference to the same function and call
let move = run;
move();
```
## hoisting
the process of function declarations to the top of the file. it is done automatically by the javascript engine.
## arguments
```javascript
function sum() {
    let total = 0;
    for (let value of arguments)
        total += value;
    return total;
}
```
## the rest operator
```javascript
function sum(...args) {
    return args.reduce((a, b) => a + b);
}
```
## default parameters
```javascript
function interest(principal, rate = 3.5, years = 5) {
    return principal * rate / 100 * years;
}
```
## getters and setters
getter: access a function result as a property   
setter: change a property
```javascript
const person = {
    firstName: 'Ling',
    lastName: 'Ouyang'，
    get fullName() {
        return `${person.firstName} ${person.lastName}`
    },
    set fullName(value) {
        const parts = value.split(' ');
        this.firstName = parts[0];
        this.lastName = parts[1];
    }
};

person.fullName = 'John Smith';

console.log(person.fullName);
```
## try and catch
```javascript
const person = {
    firstName: 'Ling',
    lastName: 'Ouyang'，
    get fullName() {
        return `${person.firstName} ${person.lastName}`
    },
    set fullName(value) {
        if (typeof value !== 'string')
            throw new Error('Value is not a string');
        const parts = value.split(' ');
        if (parts.length !== 2)
            throw new Error('Enter a first and last names')
        this.firstName = parts[0];
        this.lastName = parts[1];
    }
};
try {
    person.fullName = '';
}
catch (e) {
    console.log(e);
}

console.log(person.fullName);
```
## let, const, and var
let and const create block-scoped variables   
var creates function-scoped variables
## the this keyword
this: the object that is executing the current function   
if the function is a method under an object, 'this' refers to the object   
if the function is a regular function, 'this' refers to the global object (the window object of browser or the global object of node)   
```javascript
const video = {
    title: 'a',
    play() {
        console.log(this);
    }
};

video.stop = function() {
    console.log(this);
}

video.stop(); // get the play object
```
```javascript
const video = {
    title: 'a',
    play() {
        console.log(this);
    }
};

function playVideo() {
    console.log(this);
}

playVideo(); // get the window object
```
## change 'this'
```javascript
// using a new object, not recommended
const video = {
    title: 'a',
    tags: ['a', 'b', 'c'],
    showTags() {
        const that = this;
        this.tags.forEach(function(tag) {
            console.log(that.title, tag);
        });
    }
};

video.showTags();
```
```javascript
function playVideo() {
    console.log(this);
};

playVideo.call({ name: 'Ling'}); // will log the object
playVideo.apply({ name: 'Ling'}); // will log the object

playVideo(); // will log the window object

```
```javascript
// using bind
const video = {
    title: 'a',
    tags: ['a', 'b', 'c'],
    showTags() {
        this.tags.forEach(function(tag) {
            console.log(this.title, tag);
        }.bind(this));
    }
};

video.showTags();
```
```javascript
// using an arrow function, which inherites 'this' from the containing function
const video = {
    title: 'a',
    tags: ['a', 'b', 'c'],
    showTags() {
        this.tags.forEach(tag => {
            console.log(this.title, tag);
        });
    }
};

video.showTags();
```
