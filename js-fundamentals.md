# JS Fundamentals

## Statements - A thought or process to run in Javascript (usually terminated in a semicolon).

```js
var x = 2;

// Also multiple lines can be a statement
document.querySelector('a')
  .color = 'red';
```

## Variables - Places to store data

* `var` - Simplest variable type (hoists to the top of function scope)
* `const` - Once assigned the value cannot be changed (scopes to nearest function OR if/while/catch block)
* `let`- Does not hoist, can be reassigned (scopes to nearest function OR if/while/catch block)

```js
x; // undefined because this hoists
if (var x = 3) {
  let y = 2;
}

const z = 5;

z = 6; // Error because 'const' cannot be reassigned

y + 2; // Error because `let` is scoped to the if statement
```

## Data Types

* Numbers
  * Negative
  * Whole Numbers
  * Decimals
  * 0
  * `NaN`
* Strings
* Booleans
* Arrays
* Objects
* `null`
* `undefined`

## Strings - List of characters in a row

Regular Strings can use double or single quotes

Template Strings (backticks) allow a few extra nice things

* Multiple lines
* Variable "interpolation" (you got Javascript in your strings in your Javascript)

```js
const a = 'basic string';
const b = 'basic\nMultiple\nLineString';
const c = 'basic string that' + a; // basic string thatbasic string
const d = 'basic string that \'' + a + '\''; // basic string that 'basic string'

const e = `basic
Multiple
LineString`;
const f = `basic string that ${a}`; // basic string that basic string
const g = `basic string that '${a}'`; // basic string that 'basic string'
```

## Functions - Stored and reusable pieces of code that can be changed based on input and return output

### Named functions - Hoist to top of parent scope

```js
x(); // This works

function x() {
  return 3;
}

x();
```

### Anonymous Functions - Take on hoisting/assignment rules of the variable they are assigned to

```js
x(); // Errors because x is undefined
z(); // This would be fine

var x = function z() {
  return 3;
}

x(); // 3
```

### Fat Arrow - Shorthand for "Anonymous Functions"... Also binds `this` to wherever the function was created.

```js
var x = () => {
  return 3;
};

// Shorthand "implicit return" returns the right side of the arrow
var y = () => 3;
var z = (a, b) => a + b;

y; // Function
y(); // 3
```

Change context: http://codepen.io/rtablada/pen/peErNG?editors=1010

### Arguments/Parameters - Variables that are named inputs for functions

Arguments are replaced in the order they are given to a function

```js
function difference(a, b) {
  return a - b;
}

difference(3, 5); // -2

// Default values for arguments
function sum(a = 1, b = 1) {
  return a + b;
}

sum(2); // 3
```

Unless a function has defaults, arguments that are not passed in will be `undefined`.

### Callbacks - When we use a function as an argument to another function

```js
function takesCallback(cb) {
  return cb(3);
}

function x(a) {
  return a * 2;
}

function y(a) {
  return a - 2;
}

takesCallback(x); // 6
// |-  x(3);
//     |-  2 * 3;

takesCallback(y); // 1
// |-  y(3);
//     |-  3 - 2;

takesCallback(3); // Error NUMBER is not a function
```

Often used for Array Functions

```js
var x = [1, 2, 3];

const log = function(a) {
  console.log(a);
};

x.forEach(log);

log('abc');

// Can also be an anonymous function inline
const sum = x.reduce((a, b) => a + b); // 6
```

Also helpful for asynchronous work:

```js
// Runs the callback after >300ms
window.setTimeout(() => {
  console.log('later');
}, 300);
```
