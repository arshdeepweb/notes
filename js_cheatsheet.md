
# JavaScript Cheatsheet

## 1. Basics of JavaScript

### Variables
```javascript
var name = "John";   // Global/function-scoped, reassignable
let age = 30;        // Block-scoped, reassignable
const pi = 3.1416;   // Block-scoped, non-reassignable
```

### Data Types
- **Primitive**: `Number`, `String`, `Boolean`, `Null`, `Undefined`, `Symbol`, `BigInt`
- **Non-Primitive**: `Object`, `Array`, `Function`

```javascript
const str = "Hello";  // String
const num = 42;       // Number
const bool = true;    // Boolean
const arr = [1, 2, 3]; // Array (Object)
const obj = {name: "Alice", age: 25}; // Object
const func = function() {};  // Function
```

### Comments
```javascript
// Single-line comment
/* Multi-line 
   comment */
```

## 2. Operators

### Arithmetic
```javascript
+  // Addition
-  // Subtraction
*  // Multiplication
/  // Division
%  // Modulus (remainder)
** // Exponentiation
```

### Comparison
```javascript
==  // Equal to (type coercion)
=== // Strict equal to (no type coercion)
!=  // Not equal to
!== // Strict not equal to
<   // Less than
>   // Greater than
<=  // Less than or equal to
>=  // Greater than or equal to
```

### Logical
```javascript
&& // Logical AND
|| // Logical OR
!  // Logical NOT
```

### Assignment
```javascript
=   // Assign
+=  // Add and assign
-=  // Subtract and assign
*=  // Multiply and assign
/=  // Divide and assign
```

## 3. Control Flow

### Conditional Statements
```javascript
if (condition) {
  // code block
} else if (anotherCondition) {
  // code block
} else {
  // code block
}
```

### Switch Statement
```javascript
switch (expression) {
  case 'value1':
    // code block
    break;
  case 'value2':
    // code block
    break;
  default:
    // default code block
}
```

### Ternary Operator
```javascript
condition ? expr1 : expr2;
```

## 4. Loops

### For Loop
```javascript
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

### While Loop
```javascript
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
```

### Do-While Loop
```javascript
let i = 0;
do {
  console.log(i);
  i++;
} while (i < 10);
```

### For...of Loop (arrays)
```javascript
const arr = [1, 2, 3];
for (const num of arr) {
  console.log(num);
}
```

### For...in Loop (objects)
```javascript
const obj = {a: 1, b: 2};
for (const key in obj) {
  console.log(key, obj[key]);
}
```

## 5. Functions

### Function Declaration
```javascript
function greet(name) {
  return "Hello, " + name;
}
```

### Function Expression
```javascript
const greet = function(name) {
  return "Hello, " + name;
};
```

### Arrow Function (ES6)
```javascript
const greet = (name) => "Hello, " + name;
```

## 6. Objects

### Creating an Object
```javascript
const person = {
  name: "John",
  age: 30,
  greet: function() {
    console.log("Hello, " + this.name);
  }
};
```

### Accessing Object Properties
```javascript
person.name; // Dot notation
person['age']; // Bracket notation
```

### Object Methods
```javascript
person.greet();  // Calling method
```

## 7. Arrays

### Creating an Array
```javascript
const arr = [1, 2, 3, 4];
```

### Common Array Methods
```javascript
arr.push(5);  // Adds 5 at the end
arr.pop();    // Removes the last element
arr.shift();  // Removes the first element
arr.unshift(0); // Adds 0 to the beginning
arr.length;   // Returns array length
```

### Iterating Arrays
```javascript
arr.forEach(function(item) {
  console.log(item);
});
```

## 8. ES6 Features

### Destructuring Assignment
```javascript
const person = {name: 'John', age: 25};
const {name, age} = person;
```

### Spread Operator
```javascript
const arr1 = [1, 2];
const arr2 = [...arr1, 3, 4];  // Combines arrays
```

### Rest Parameter
```javascript
function sum(...nums) {
  return nums.reduce((acc, num) => acc + num, 0);
}
```

## 9. Promises & Async/Await

### Promises
```javascript
const myPromise = new Promise((resolve, reject) => {
  const success = true;
  if (success) {
    resolve("Success!");
  } else {
    reject("Failure.");
  }
});

myPromise.then(value => console.log(value)).catch(error => console.log(error));
```

### Async/Await
```javascript
async function fetchData() {
  try {
    const response = await fetch('url');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}
```

## 10. DOM Manipulation

### Selecting Elements
```javascript
document.getElementById('id'); // Select by ID
document.getElementsByClassName('class'); // Select by class
document.querySelector('.class'); // Select first match
document.querySelectorAll('.class'); // Select all matches
```

### Modifying Elements
```javascript
const elem = document.getElementById('id');
elem.textContent = "New Text";  // Change text content
elem.innerHTML = "<p>New HTML</p>";  // Change HTML content
elem.style.color = "red";  // Change styles
```

### Event Listeners
```javascript
button.addEventListener('click', function() {
  alert("Button clicked!");
});
```

## 11. Classes (ES6)

### Class Declaration
```javascript
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
  
  greet() {
    console.log("Hello, " + this.name);
  }
}

const john = new Person("John", 30);
john.greet();
```

### Inheritance
```javascript
class Employee extends Person {
  constructor(name, age, position) {
    super(name, age);
    this.position = position;
  }
  
  work() {
    console.log(this.name + " is working as a " + this.position);
  }
}

const emp = new Employee("Alice", 25, "Developer");
emp.work();
```

## 12. Modules (ES6)

### Exporting and Importing Modules
```javascript
// math.js
export const add = (a, b) => a + b;

// main.js
import { add } from './math.js';
console.log(add(2, 3));
```

## 13. Error Handling

### Try...Catch
```javascript
try {
  // code that may throw an error
  throw new Error("Something went wrong");
} catch (error) {
  console.log(error.message);
} finally {
  console.log("This runs no matter what");
}
```

## 14. Local Storage and Session Storage

### Local Storage (persistent)
```javascript
localStorage.setItem("key", "value");
localStorage.getItem("key");
localStorage.removeItem("key");
localStorage.clear();
```

### Session Storage (clears on tab close)
```javascript
sessionStorage.setItem("key", "value");
sessionStorage.getItem("key");
sessionStorage.removeItem("key");
sessionStorage.clear();
```

## 15. JSON Handling

### Parsing JSON
```javascript
const jsonString = '{"name": "John", "age": 30}';
const obj = JSON.parse(jsonString);
console.log(obj.name);  // Access parsed object
```

### Stringifying Object to JSON
```javascript
const obj = {name: "John", age: 30};
const jsonString = JSON.stringify(obj);
console.log(jsonString);  // {"name":"John","age":30}
```
