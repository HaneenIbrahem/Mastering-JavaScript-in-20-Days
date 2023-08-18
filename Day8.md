# Day 8: JavaScript: The Hard Parts, v2
This README file summarizes the JavaScript lesson on Closure and Asynchronous JavaScript.

## Lesson Summary

Closure
- Closure is the most esoteric concept in JavaScript
- Enables powerful pro-level functions like ‘once’ and ‘memoize’
- Many JavaScript design patterns including the module pattern use closure
- Build iterators, handle partial application and maintain state in an 
asynchronous world

**Note:** function never remember anything from their previous running.

**Functions with memories**
- When our functions get called, we create a live store of data (local 
memory/variable environment/state) for that function's execution context.
- When the function finishes executing, its local memory is deleted (except the returned value)
- But what if our functions could hold on to live data between executions? 
- This would let our function definitions have an associated cache/persistent memory
- But it all starts with us returning a function from another function

:tw-25b6: Closure created when a function defined inside other function and the inner function still have access to the variables & parameters of the outer function even the outer function has finished running.

**functions can be returned from other functions in JS** like this example:
```JavaScript
function createFunction() {
 function multiplyBy2 (num){
 return num*2;
 }
 return multiplyBy2;
}
const generatedFunc = createFunction();
const result = generatedFunc(3); // 6
```
[[scope]]: hodden property we can't access it.

Scope is the rules in any programmimg language for at any given line of code, what data do i have available to me?

**Backpack:** C.O.V.E , P.L.S.R.D, Closure.

C.O.V.E: Closed Over Variable Environment .

P.L.S.R.D: Persistant Lexical Static Scope Reference Data.

Closure gives our functions persistent memories and 
entirely new toolkit for writing professional code
- Helper functions
- Iterators and generators
- Module pattern
- Asynchronous JavaScript

#### Asynchronous  JS

**Promises, Async & the Event Loop**
- Promises - the most signficant ES6 feature
- Asynchronicity - the feature that makes dynamic web applications possible
- The event loop - JavaScript’s triage
- Microtask queue, Callback queue and Web Browser features (APIs)

:tw-2734: every single time we have a task to do, we must finish it before we move on.

Asynchronicity is the backbone of modern web development in JavaScript yet...

JavaScript is: 
- Single threaded (one command runs at a time)
- Synchronously executed (each line is run in order the code appears)

if we have a task : accessing Twitter's server to get new tweets that takes a long time

** Challenge: We want to wait for the tweets to be stored in tweets so that they’re there 
to run displayTweets on - but no code can run in the meantime**

**setTimeout():** is a built in function, its first argument is the function to delay followed by ms to delay by.

```JavaScript
function printHello(){
 console.log("Hello");
}
setTimeout(printHello,1000);
console.log("Me first!");

// this wil print :

//Me first
//Hello    // after 1000ms
```

Our core JavaScript engine has 3 main parts:
- Thread of execution
- Memory/variable environment
- Call stack
We need to add some new components:
- Web Browser APIs/Node background APIs
- Promises
- Event loop, Callback/Task queue and micro task queue

**Event loop:** Allow to manage multiple tasks and events concurrently without blocking the execution of code.

## DELIEVERABLES:
[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md#question-1)
```JavaScript
function createCounter(start) {
  let counter = start;

  function incrementCounter() {
    counter++;
  }

  return incrementCounter;
}

const counter = createCounter(1);
```

[Question 2](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week2%20-%20javaScript-the-hard-parts-v2/day%202/tasks.md#question-2)
```JavaScript
function calculateAverage(nums) {
    let sum = 0;
    let count = 0;
  
    function avg() {
        for (let num of nums) {
            sum += num;
            count++;
          }
        if (count === 0) {
            return 0; // Return 0 for an empty array
        }
        let average =  sum / count; 
        return average; 
    };
    return avg;
  }
  
  const avgFunction = calculateAverage([5, 10, 15, 20]);
  console.log(avgFunction()); // Outputs: 12.5
```
