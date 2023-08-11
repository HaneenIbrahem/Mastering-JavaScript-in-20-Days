# Day 4: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on Functions, Events & Handlers.

## Lesson Summary

Declare a function: 

```javascript
function half(x){
  return x/2;
}
```

- Vlaues are things.
- Variables point to things.
- functions do things.

## Exercise 1: in the console declare the following functions:
1. multiply: given 2 numbers, return their product
    ```javascript  
   function multiply(x, y){
      return x * y;
    }
2. yell: given a lowercase string log it in all caps to the console
    ```javascript 
   function yell(saying){
      return saying.toUpperCase();
    }
3. longerThan: given 2 arrays, return whether the first is longer than the second  
     ```javascript
   function longerThan(arr1, arr2){
     return arr1.length > arr2.length;
    }


**Arrow functions:** quick way to create small, simple and little function.

**=>:** called "fat arrow", let us crate an unnamed function without much code.

```javascript
const add = (x, y) => x+y

// it equivelent to the below code :

function add(x, y){
  return x+y;
}
```

## Exercise 2: declare the following functions using arrow functions:
1. divide: given 2 numbers, return the first divided by the second 
   ```javascript
   const divide = (x, y) => x/y
2. whisper: given an uppercase string, log it in all lowercase to the console
   ```javascript
   const whisper = (text) => text.toUpperCase();
3. shorterThan: given 2 arrays, return whether the first is shorter than the second
   ```javascript
   const shorterThan = (arr1, arr2) => arr1 < arr2


## Exercise 3:
1. capitalize the text of the "true" button when it is clicked
   ```javascript
   trueButton.addEventListener("click", (event) => {
      textButton.textContent = trueButton.textContent.toUpperCase();
   });
   ```
2. change the h1 text to "hovering" when the mouse moves into the element
   ```javascript
   let h1 = document.getElementByTagName("h1");
   h1 = h1[0];
   h1.addEventListener("mouseover",() => {
     h1.textContent = "hovering";
   });
   ```
## DELIEVERABLES:

1. **[Global Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/global-scope-and-functions)**
   
**Solution:** 
 ```javascript
// Declare the myGlobal variable below this line

const myGlobal = 10;

function fun1() {
  // Assign 5 to oopsGlobal here
  oopsGlobal = 5;
}

// Only change code above this line

function fun2() {
  let output = "";
  if (typeof myGlobal != "undefined") {
    output += "myGlobal: " + myGlobal;
  }
  if (typeof oopsGlobal != "undefined") {
    output += " oopsGlobal: " + oopsGlobal;
  }
  console.log(output);
}
```

2. **[Local Scope and Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)**
   
**Solution:**
 ```javascript
function myLocalScope() {
  // Only change code below this line
  let myVar = "Haneen"
  console.log('inside myLocalScope', myVar);
}
myLocalScope();

// Run and check the console
// myVar is not defined outside of myLocalScope
console.log('outside myLocalScope', myVar);
```

3. **[Global vs. Local Scope in Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/local-scope-and-functions)**
   
**Solution:**
 ```javascript
// Setup
const outerWear = "T-Shirt";

function myOutfit() {
  // Only change code below this line
  const outerWear = "sweater";
  // Only change code above this line
  return outerWear;
}

myOutfit();
```
4. **[Stand in Line](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/stand-in-line)**

**Solution:**
 ```javascript
function nextInLine(arr, item) {
  // Only change code below this line
  arr.push(item);
   item = arr.shift();
  return item;
  // Only change code above this line
}

// Setup
let testArr = [1, 2, 3, 4, 5];

// Display code
console.log("Before: " + JSON.stringify(testArr));
console.log(nextInLine(testArr, 6));
console.log("After: " + JSON.stringify(testArr));
```

