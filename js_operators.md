# JS operators
## arithmetic operators
basics
```javascript
let x = 10;
let y = 3;
console.log(x + y);
console.log(x - y);
console.log(x * y);
console.log(x / y);
console.log(x % y);
console.log(x ** y);
```
increment
```javascript
let x = 10;
console.log(++x); // x was incremented by 1 first, then to console, this gets 11
console.log(x++); // see x on the console first, then incremented by 1, gets 10 but the x is now 11
```
decrement
```javascript
let x = 10;
console.log(--x); // x was decremented by 1 first, then to console, this gets 9
console.log(x--); // see x on the console first, then decremented by 1, gets 10 but the x is now 9
```
## assignment operators
```javascript
let x = 10;
// three ways of increment by one
x = x + 1;
x++;
x += 1;
// more examples
x = x + 5;
x += 5;

x = x * 3;
x *= 3;
```
## comparison operators
```javascript
let x = 1;
// relational
console.log(x > 0); // true
console.log(x >= 1); // true
console.log(x < 1); // false
console.log(x <= 1); // true
// equality
console.log(x === 1); // true
console.log(x !== 1); // false
```
different equals
```javascript
// strict equality: same type and same value
console.log(1 === 1); // true
console.log('1' === 1); // false
// loose equality:
console.log(1 == 1); // true
console.log('1' == 1); // true
console.log(true == 1); // true
```
## ternary operator
```javascript
// if a customer has more than 100 points: gold; else: silver
let points = 110;
let type = points > 100 ? 'gold' : 'silver';
console.log(type);
```
## logical operators
### logical AND: &&
```javascript
console.log(true && true); // true
console.log(false && true); // false
```
### logical OR: ||
```javascript
console.log(true || true); // true
console.log(false || true); // true
```
### NOT: !
```javascript
let highIncome = false;
let goodCreditScore = false;
let eligibleForLoan = highIncome || goodCreditScore;
let applicationRefused = !eligibleForLoan;
console.log(applicationRefused); // true
```
## logical operators with non-booleans
```javascript
false || true // true
false || 'Ling' // 'Ling'
false || 1 // 1

```
### falsy (false) values
undefined   
null   
0   
false   
''   
NaN   
### truthy values
anything that is not falsy
### short circuting
```javascript
false || 1 || 2 // 1
```
a useful example
```javascript
let userColor = 'red';
let defaultColor = 'blue';
let currentColor = userColor || defaultColor;
console.log(currentColor) // 'red'
let userColor = undefined;
console.log(currentColor) // 'blue'
```
## bitwise operators
```javascript
// 1 = 00000001
// 2 = 00000010
console.log(1 | 2); // bitwise OR
console.log(1 & 2); // bitwise AND
```
example
```javascript
// read, write, execute
// 00000100
// 00000010
// 00000001
const readPermission = 4;
const writePermission = 2;
const executePermission = 1;
let myPermission = 0;
myPermission = myPermission | readPermission | writePermission;
console.log(myPermission); // 6
let message =
    (myPermission & readPermission) ? 'yes' : 'no';
console.log(message); // yes
```
