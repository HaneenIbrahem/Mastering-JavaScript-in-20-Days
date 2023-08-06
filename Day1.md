Day 1: Hoisting
This README file summarizes the JavaScript lesson on hoisting. Hoisting is a behavior in JavaScript where variable and function declarations are moved to the top of their scope during the compilation phase.

Lesson Summary
In this lesson, we explored hoisting in JavaScript. Here are the key points covered:

Hoisting is the process of moving variable and function declarations to the top of their scope.
Variable declarations are hoisted but not their assignments. They are accessible but have an initial value of undefined.
Function declarations are also hoisted, allowing them to be called before they are defined.
Hoisting does not apply to function expressions, arrow functions, or variables declared with let or const.
Coding Examples
// Example 1: Variable Hoisting
console.log(x); // Output: undefined
var x = 10;
console.log(x); // Output: 10

// Example 2: Function Hoisting
hoistedFunction(); // Output: "Hello, World!"

function hoistedFunction() {
  console.log("Hello, World!");
}
Coding Exercises
Factorialize a Number
My Solution
// Example 1: Variable Hoisting
console.log(x); // Output: undefined
var x = 10;
console.log(x); // Output: 10

// Example 2: Function Hoisting
hoistedFunction(); // Output: "Hello, World!"

function hoistedFunction() {
  console.log("Hello, World!");
}
