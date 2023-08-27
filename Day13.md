# Day 13: Deep JavaScript Foundations, v3
This README file summarizes the JavaScript lesson on Scope, Scope & Function Expressions and Scope & Function Expressions

## Lesson Summary

**Scope**

scope in programming defines where variables and functions are accessible and determines their visibility and lifetime. Global scope refers to variables accessible throughout the program, while local scope refers to variables accessible within a specific function or block.

1. Global Scope:
```javascript
var globalVar = 10;
function myFunction() {
  console.log(globalVar); // Accessible in the function
}
```
2. Local Scope:
```javascript
function myFunction() {
  var localVar = 20; // Local variable
  console.log(localVar); // Accessible within the function
}
console.log(localVar); // Error: localVar is not defined outside the function
```

Lexical scope, also known as static scope, is a concept in programming languages that defines how variables and names are resolved in nested functions or blocks based on their position in the source code.

lexical scope is used to determine which variables are accessible in a given context.

Dynamic global variables:
```javascript
var x = 10;

function outer() {
  function inner() {
    console.log(x); // Accesses the global variable x
  }
  inner();
}

function another() {
  var x = 20;
  outer();
}

another(); // Outputs 20, not 10
```

in the example below:
 the inner function accesses the global variable x because it's not defined in its local scope. However, the value of x that it accesses is determined by the call stack at runtime, and in this case, it's the value from the another function's local scope.
```javascript
var x = 10;

function outer() {
  function inner() {
    console.log(x); // Accesses the global variable x
  }
  inner();
}

function another() {
  var x = 20;
  outer();
}

another(); // Outputs 20, not 10

```

variables declared with var, let, or const have lexical scope, which means their accessibility is determined by the position in the code's nested functions, providing more predictable behavior compared to dynamically scoped variables.

**Strict mode** is a feature in JavaScript that enforces stricter parsing and error handling rules for the code.

i should add this line to the code:
`'use strict';`

------

**Anonymous Function Expression:**
```javascript
const greet = function(name) {
  console.log(`Hello, ${name}!`);
};

greet("Alice"); // Output: Hello, Alice!

```

**Named Function Expression:**
```javascript
const addNumbers = function sum(a, b) {
  return a + b;
};

console.log(addNumbers(3, 5)); // Output: 8
```

**Using Function Expression as a Callback:**
```javascript
const numbers = [1, 2, 3, 4, 5];

const doubled = numbers.map(function(num) {
  return num * 2;
});

console.log(doubled); // Output: [2, 4, 6, 8, 10]
```

**Arrow Function without Parameters:**
```javascript
const sayHello = () => {
  console.log("Hello!");
};

sayHello(); // Output: Hello!

```

**Arrow Function with Parameters:**
```javascript
const add = (a, b) => {
  return a + b;
};

console.log(add(3, 5)); // Output: 8
```

**Arrow Function with Implicit Return:**
```javascript
const multiply = (x, y) => x * y;

console.log(multiply(2, 4)); // Output: 8
```

**Arrow Function as Callback:**
```javascript
const numbers = [1, 2, 3, 4, 5];

const squared = numbers.map(num => num * num);

console.log(squared); // Output: [1, 4, 9, 16, 25]
```
---
function types hierarchy :

1. Function Declarations:

```javascript
function add(a, b) {
  return a + b;
}
```
2. Function Expressions:

```javascript
const multiply = function(x, y) {
  return x * y;
};

```

3. Arrow Functions:

```javascript
const square = x => x * x;

```

4. Method Functions:

```javascript
const calculator = {
  add: function(a, b) {
    return a + b;
  }
};

```

5. Constructor Functions:

```javascript
function Person(name, age) {
  this.name = name;
  this.age = age;
}
const person = new Person("Alice", 30);

```

6. Higher-Order Functions:

```javascript
const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map(number => number * 2);

```

7. IIFE (Immediately Invoked Function Expression):

```javascript
(function() {
  // Code here
})();

```

8. Generator Functions:

```javascript
function* countUp() {
  let count = 0;
  while (true) {
    yield count++;
  }
}

```

**block scoping is introduced with the `let` and `const` keywords.**

In this example, the variable x is defined within the block of the if statement. It is accessible only within that block and not outside of it.
```javascript
function example() {
  if (true) {
    let x = 10; // x is scoped to this block
    console.log(x); // Output: 10
  }
  // x is not accessible here
}

example();
```

In this example, the variable y defined with var is scoped to the entire function, making it accessible both inside and outside the if block
```javascript
function example() {
  if (true) {
    var y = 20; // y is scoped to the function
    console.log(y); // Output: 20
  }
  console.log(y); // Output: 20 (accessible outside the block)
}

example();
```

choosing `let` or `var`

1. Block Scoping:

- let: Variables declared with let are block-scoped. They are only accessible within the block of code where they are defined.
- var: Variables declared with var are function-scoped or globally scoped, but not block-scoped. They are accessible throughout the entire function or even globally if declared outside of any function.
 
2. Hoisting:

- let: Variables declared with let are hoisted to the top of their block scope, but they are not initialized. This means you cannot access them before the line where they are declared.
- var: Variables declared with var are hoisted to the top of their function scope or global scope and are initialized with the value undefined. This can lead to unexpected behavior if you try to use them before they are declared.

3. Re-declaration:

- let: You cannot re-declare a variable with let in the same block scope. Attempting to do so will result in an error.
- var: You can re-declare a variable with var in the same scope without any error.

4. Function Scoping vs. Block Scoping:

- let introduces block scoping, which aligns with modern programming practices and helps prevent variable leaks and unexpected behavior.
- var uses function scoping, which can lead to unintentional variable sharing across different parts of a function.

-----
Variable Hoisting:
```javascript
console.log(myVar); // undefined
var myVar = 42;
```

Function Hoisting: can call the function before it's declared in the code.
```javascript
greet(); // "Hello!"
function greet() {
  console.log("Hello!");
}
```

However, function expressions are not hoisted in the same way:

```javascript
greet(); // Error: greet is not a function
var greet = function() {
  console.log("Hello!");
};
```
In this case, only the variable greet is hoisted, not the function assigned to it.


**var Hoisting:**

```javascript
console.log(myVar); // undefined
var myVar = 42;
```
**let Hoisting and Temporal Dead Zone (TDZ):**

```javascript
console.log(myLet); // ReferenceError: Cannot access 'myLet' before initialization
let myLet = 42;
```

## DELIEVERABLES 1:

1. **[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%203/tasks.md#question-1)**
   
**Solution:** 
 ```javascript

const exampleNormalFunc1 = (a, b, c) => {
  return a * (b + c);
}

const exampleNormalFunc2 = (x, y) => {
  return x * y;
}

const exampleNormalFunc3 = (string) => {
  return string + " " + string + " " + string + "!";
}


const arrowHOF = (normalFunc) => {
    return (...args1) => {
        return (...args2) => {
            const result = normalFunc(...args1);
            for (let i = 0; i < args2; i++) {
                console.log(result);
            }
            return result;
        };
    };
};

const hofNormalFunc1 = arrowHOF(exampleNormalFunc1);
const hofNormalFunc2 = arrowHOF(exampleNormalFunc2);
const hofNormalFunc3 = arrowHOF(exampleNormalFunc3);

console.log(hofNormalFunc1(3, 4, 5)(2)); // logs 60 twice
console.log(hofNormalFunc2(20, 35)(4)); // logs 700 four times
console.log(hofNormalFunc3("Meow")()); // logs "Meow Meow Meow!" once

```

2. **[Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%202/tasks.md#question-2)**
   
**Solution:**

```javascript
const preserveThis = (func) => {
    return func.bind(obj);
  };
  
  const obj = {
    name: 'John',
    greet: function (greeting) {
      console.log(`${greeting}, ${this.name}!`);
    }
  };
  
  const preservedGreet = preserveThis(obj.greet);
  
  preservedGreet('Hello'); // Output: "Hello, John!"
```

3. **[Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%203/tasks.md#question-3)**
   
**Solution:**

*Reasoning for Example 1's Output:*

The variable x is accessible to the inner1 function due to lexical scoping. The function inner1 looks for the variable x in its own scope first and then in the parent scope (which is outer1's scope). Since there's no variable named x inside the scope of inner1, it accesses the x variable from the parent scope, which is 10.

*Reasoning for Example 1's Output:*

The variable x inside the inner2 function is a separate variable from the x variable in the parent scope of outer2. The concept of lexical scoping ensures that inner functions have access to variables in their parent scope, but if a variable with the same name is declared inside the inner function's scope, it will shadow (hide) the variable from the parent scope. In this case, the inner2 function prints the value of its own local x variable, which is 20.

------
## DELIEVERABLES 2:

1. **[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%204/tasks.md#question-1)**
   
**Solution:** 

```javascript
for (var i = 0; i < 5; i++) {
  (function(index) {
    setTimeout(function() {
      console.log("value of [i] is: ", index);
    }, 100);
  })(i);
}
```

2. **[Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%204/tasks.md#question-2)**
   
**Solution:** 

```javascript
let array = [];

for (let i = 0; i < 5; i++) {
   array.push(i);
   console.log("Current array is:", array);
}
```

3. **[Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%204/tasks.md#question-3)**
   
**Solution:** 

```javascript
let functions = [];

for (let i = 0; i < 5; i++) {
  functions.push(() => {
    console.log("Current value of i is:", i);
  });
}

functions.forEach((func) => func());
```
