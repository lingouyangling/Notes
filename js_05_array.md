## adding elements
```javascript
const numbers = [3, 4];

numbers.push(5, 6) // add to the end

numbers.unshift(1, 2) // add to the beginning

numbers.splice(2, 0, 'a', 'b') // add in the middle
```
## finding elements
### value types
```javascript
const numbers = [1, 2, 3, 1, 4];

numbers.indexOf(1); // get 0
numbers.indexOf('a'); // get -1

numbers.lastIndexOf(1); // get 3

numbers.includes(1); // get true
```
### reference types
```javascript
const courses = [
    { id: 1, name: 'a' },
    { id: 2, name: 'b' },
];

const course = courses.find(function(course) {
    return course.name === 'a';
}); // get true

const course = courses.findIndex(function(course) {
    return course.name === 'a';
}); // get 0
```
## arrow function (similar to lambda in python)
```javascript
const courses = [
    { id: 1, name: 'a' },
    { id: 2, name: 'b' },
];

const course = courses.find(course => course.name === 'a'); // get true
```
## removing elements
```javascript
const numbers = [1, 2, 3, 4];

numbers.pop(); // remove the last element

numbers.shift(); // remove the first element

numbers.splice(2, 1); // remove from the middle
```
## emptying an array
```javascript
let numbers = [1, 2, 3, 4];

numbers = []; // does not work if multiple references to the array

numbers.length = 0;

numbers.splice(0, numbers.length);

while (numbers.length > 0)
    numbers.pop();

```
## combining and slicing
```javascript
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = first.concat(second);

const slice = combined.slice(2, 4);
```
## spread operator
```javascript
const first = [1, 2, 3];
const second = [4, 5, 6];

const combined = [...first, ...second];

const copy = [...combined];
```
## iterating an array
```javascript
const numbers = [1, 2, 3];

for (let number of numbers)
    console.log(number);

numbers.forEach(number => console.log(number));

numbers.forEach((number, index) => console.log(index, number));
```
## join arrays
```javascript
const numbers = [1, 2, 3];
const joined = numbers.join(','); // a string

const message = 'This is my first message';
const parts = message.split(' ');
```
## sort
```javascript
const numbers = [2, 3, 1];
numbers.sort(); //asc
numbers.reverse(); //desc
```
```javascript
const courses = [
    { id: 1, name: 'Node.js' },
    { id: 2, name: 'Javascript' },
];

courses.sort(function(a, b) {
    if (a.name < b.name) return -1;
    if (a.name > b.name) return 1;
    return 0;
});
```
## test the elements of an array
```javascript
const numbers = [1, 2, 3];

const allPositive = numbers.every(function(value) {
    return value >= 0;
});

const atLeastOnePositive = numbers.some(function(value) {
    return value >= 0;
});
```
## filter
```javascript
const numbers = [1, -1, 2, 3];

const filtered = numbers.filter(n => n >= 0;);
```
## map
```javascript
const numbers = [1, -1, 2, 3];

const filtered = numbers.filter(n => n >= 0;);

const items = filtered.map(n => '<li>' + n + '</li>');

const html = '<ul>' + items.join('') + '</ul>';
```
## reduce
```javascript
const numbers = [1, -1, 2, 3];

const sum = numbers.reduce(
    (accumulator, currentValue) => accumulator + currentValue, 0);
```
