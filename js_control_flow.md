## if else
```javascript
// hour
// if hour is between 6am and 12pm: good morning
// 12pm to 6pm: good afternoon
// otherwise: good evening
let hour = 10;
if (hour >= 6 && hour < 12) {
    console.log('Good Morning');
}
else if (hour >= 12 && hour < 18) {
    console.log('Good Afternoon');
}
else {
    console.log('Good Evening');
}
```
## switch case
```javascript
let role = 'guest';

switch (role) {
    case 'guest':
        console.log('Guest User');
        break;
    case 'moderator':
        console.log('Moderator User');
        break;
    default:
        console.log('Unknown User');
}
```
## for loop
```javascript
for (let i = 0; i < 5; i++) {
    if (i % 2 !== 0)
        console.log('Hello World');
}
```
## while loop
```javascript
let i = 0;
while (i < 5) {
    if (i % 2 !== 0)
        console.log('Hello World');
    i++;
}
```
## do while
```javascript
let i = 0;
do {
    if (i % 2 !== 0)
        console.log('Hello World');
    i++;
} while (i < 5);
```
## for in
```javascript
const person = {
    name: 'Ling',
    age: 30
};
for (let key in person) // iterate over the keys
    console.log(key, person[key]);

const colors = ['red', 'green', 'blue'];
for (let index in colors) // iterate over the indices
    console.log(index, colors[index]);
```
## for of
```javascript
const colors = ['red', 'green', 'blue'];
for (let color of colors) // iterate over the items
    console.log(color);
```
## break and continue
```javascript
let i = 0;
while (i <= 10) {
    if (i === 5) break;
    console.log(i);
    i++;
}
```
```javascript
let i = 0;
while (i <= 10) {
    if (i % 2 === 0) {
        i++;
        continue;
    }
    console.log(i);
    i++;
}
```
