# Day 1: JavaScript: The Hard Parts, v2
This README file summarizes the JavaScript lesson on Introduction, Principles, Functions and Call backs.

## Lesson Summary
When JS code runs?
- Goes through the code 
line-by-line and runs/ 'executes’ 
each line - known as the **thread 
of execution**
- Saves ‘data’ like strings and 
arrays so we can use that data 
later - in its **memory**

**Note:** we also can save code (functions).

**Execution Context:** Created to run the code of a function, it has 2 parts :
1. Thread of execution.
2. Memory.

**Call Stack:** 
- JS keeps track of what function is currently running
- Run a function - add to call stack
- Finish running the function - JS 
removes it from call stack
- Whatever is top of the call stack -> that's the function we're currently running
_______________
### Callbacks & Functions:

- Makes our code more declarative and readable.
- Enables map, filter, reduce (powerful pro-level functions)

**Why do we have functions?**
- make it reusable.

**DRY (Don't Repeat Yourself)**

```JavaScript
function tenSquared() {
 return 10*10;
}
tenSquared() // 100
```
We make it reusable like this :
```JavaScript
function squareNum(num){
 return num*num;
}
squareNum(10); // 100
squareNum(9); // 81
squareNum(8); // 64
```

**Generalizing functions**
'Parameters' (placeholders) -> provide an actual value ('argument') when we run the function

**Pair programming:** The most effective way to grow as a software engineer.

- Tackle blocks with a partner
- Stay focused on the problem
- Refine technical communication
- Collaborate to solve problem

Functions in javascript = first class objects (It contains all the features of the object).
- Assigned to variables and properties of other objects
- Passed as arguments into functions
- Returned as values from functions

**Higher Order Function:** The outer function that takes in a function

**Callback Function:** The function we insert.

**Higher-order functions:** Takes in a function or passes out a function.

**Callbacks and Higher Order Functions simplify our code and keep it DRY**
- Declarative readable code: Map, filter, reduce - the most readable way to write code to work with data.
- Codesmith & pro interview prep: One of the most popular topics to test in interview both for Codesmith and mid/senior level job interviews.
- Asynchronous JavaScript: Callbacks are a core aspect of async JavaScript, and are 
under-the-hood of promises, async/await.

**Introducing arrow functions - a shorthand way to save functions**
```JavaScript
function multiplyBy2(input) { return input * 2; }
```
```JavaScript
const multiplyBy2 = input => input*2
```
### Very importamt notes:

1. map(): Transform each element of an array and returns a new array with the modified values.
```JavaScript
const numbers = [1,2,3];
const double = numbers.map(function(num){
	return num * 2;
});
```
2. filter(): creates anew array containing elements that satisfy a specific condition.
```JavaScript
const numbers = [1,2,3,4,5,6];
const even = numbers.filter(function(num){
	return num%2 === 0;
});
```
3. reduce(): Accumulate values from an array into a single value (eg: sum, product, string concatenation)
```JavaScript
const numbers = [1,2,3,4,5];
const sum = numbers.reduce(function(accumulator, currentValue){
	return accumulator + currentValue;
}, 0);
```

## DELIEVERABLES:
