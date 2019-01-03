## basics
an object is a collection of key-value pairs
```javascript
const circle = {
    radius: 1,
    location: {
        x: 1,
        y: 1
    }
    isVisible: true
    draw: function() {
        console.log('draw');
    }
};

circle.draw();
```
## factory functions
```javascript
function createCircle(radius) {
    return {
        radius,
        draw() {
            console.log('draw');
        }
    };
}

const circle1 = createCircle(1);
console.log(circle1);

const circle2 = createCircle(2);
console.log(circle2);
```
## constructor functions
```javascript
function Circle(radius) {
    this.radius = radius;
    this.draw = function() {
        console.log('draw');
    }
}

const circle = new Circle(1);
```
## dynamic nature of objects
```javascript
const circle = {
    radius: 1
};

circle.color = 'yellow';
circle.draw = function() {};

delete circle.color;
delete circle.draw;
```
## constructor property
```javascript
circle.constructor // show the function that created the object
```
## functions are objects
## value vs reference
### value types
values stored in variables   
number   
string   
boolean   
symbol   
undefined   
null   
### reference types
values not stored in variable, it refers to somewhere in the memory   
object   
function   
array   
## enumerating properties of an object
```javascript
const circle = {
    radius: 1,
    draw() {
        console.log('draw');
    }
};

for (let key in circle)
    console.log(key, circle[key]);

for (let key of Object.keys(circle))
    console.log(key);

for (let entry of Object.entries(circle))
    console.log(entry);
```
## cloning an object
clone every property and method
```javascript
const circle = {
    radius: 1,
    draw() {
        console.log('draw');
    }
};

const another = {};

for (let key in circle)
    another[key] = circle[key];
```
assign (inherite)
```javascript
const circle = {
    radius: 1,
    draw() {
        console.log('draw');
    }
};

const another = Object.assign({}, circle);
```
bread operator
```javascript
const circle = {
    radius: 1,
    draw() {
        console.log('draw');
    }
};

const another = { ...circle };
```
## date
```javascript
const now = new Date() // current date time
const date1 = new Date('January 2 2019 09:00');
const date2 = new Date(2019, 0, 2, 9);

now.getDate();
now.setFullYear(2018);
now.toDateString();
now.toTimeString();
now.toISOString();
```
