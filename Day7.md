# Day 7: JavaScript: The Hard Parts, v2
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
1. [Use Higher-Order Functions map, filter, or reduce to Solve a Complex Problem](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/use-higher-order-functions-map-filter-or-reduce-to-solve-a-complex-problem)

```JavaScript
const squareList = arr => {
  // Only change code below this line 
  return arr.reduce(function(result, num){
    if(num > 0 && Number.isInteger(num)){
      result.push(num * num);
    }
    return result;
  }, []);
  // Only change code above this line
};

const squaredIntegers = squareList([-3, 4.8, 5, 3, -3.2]);
console.log(squaredIntegers);
```

2. [Apply Functional Programming to Convert Strings to URL Slugs](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/functional-programming/apply-functional-programming-to-convert-strings-to-url-slugs)

```JavaScript
// Only change code below this line
function urlSlug(title) {
  return title.toLowerCase().split(" ").filter(function(text){
    return text !=="";
  }).join("-")
}
// Only change code above this line
urlSlug("A Mind Needs Books Like A Sword Needs A Whetstone");
```
3. [Exercises for functions and callbacks](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%201/tasks.md)

Question 1: 
```JavaScript
function mapAsync(array, callback) {
  const mappedPromises = array.map(element => {
    return new Promise(resolve => {
      // Perform the asynchronous mapping using the callback
      callback(element).then(mappedValue => {
        resolve(mappedValue);
      });
    });
  });

  return Promise.all(mappedPromises);
}
```
Question 2:
```JavaScript
function sumRange(start, end) {
    if (start === end) {
      return start;
    } else{
        return start + sumRange(start + 1, end);
    }
  }

  console.log(sumRange(1, 1));
```
