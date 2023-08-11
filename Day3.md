# Day 1: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on Arrays, Objects and Quiz project. 

## Lesson Summary

Declare array: let arr1 = [];

Declare and assign : let arr2 = ["A", "B"];

## Exercise 1: What do you think each of these does:
1. ["c", "a", "d", "b"].sort();

  It sort alphabetically.
  The output: ["a", "b", "c", "d"]
    
2. ["lion", "tiger", "bears oh my!"].join(" &");

  "lions & tiger & bear oh my!"
   
3. [1,2,3].concat([4,5,6])

   [1,2,3,4,5,6]
   
##
```javascript
let abcArray = ["a", "b", "c"];
abcArray[1] = "d";
abcArray;
```
The output: ["a", "d", "c"].

```javascript
let abcString = "abc";
abcString[1] = "d";
abcString;
```
The output: "abc".

**Notes:** 
- Arrays are mutable (data can be edited).
- Strings are immutable (data always stay the same).

 ##
```javascript
let numbers1 = [1,2,3];
let result1 = numbers1.push(4);
numbers1;
```
The output: [1,2,3,4].

**push() change numbers1 and result1**

```javascript
let numbers2 = [1,2,3];
let result2 = numbers2.concat([4]);
numbers2;
```
The output: 
  result2 => [1,2,3,4].
  numbers2 => [1,2,3].

**concat() create a new object (ما بغير على الاصلية).**

**Notes:**
1. Some actions mutate an array

  (oldarray.push(newArray)) -> change the array in place.

2. Other actions don't mutate the original array, but instead create a new copy.

   (oldArray.concat(newArray)).

3. Also variables can be (im)mutable
   - let: mutable.
   - const: immutable.

## Objects

Collect multiple values together to descripe more complex data.

**Arrays are objects.**

**this:** in a method let us to reference other properties on the object.


## Exercise 2: TODO 1 + 2 + 3
1. TODO 1
   ```javascript
   const statement = document.getElementById("statement");
    const optionButtons = document.querySelectorAll("button");
    const explanation = document.getElementById("explanation");
2. TODO 2
   ```javascript
   const fact = {
        statement: "Arrays are like objects",
        answer: true,
        explanation: "Arrays are kind of object with secial proparties",
    };
3. TODO 3
   ```javascript
   statement.textContent = fact.statement;


## DELIEVERABLES:

1. **[Copy Array Items Using slice()](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/copy-array-items-using-slice)**
   
**Solution:** 
 ```javascript
function forecast(arr) {
  // Only change code below this line
  return arr.slice(2,4);
}

// Only change code above this line
console.log(forecast(['cold', 'rainy', 'warm', 'sunny', 'cool', 'thunderstorms']));
```

2. **[Combine Arrays with the Spread Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-data-structures/combine-arrays-with-the-spread-operator)**
   
**Solution:**
 ```javascript
function spreadOut() {
  let fragment = ['to', 'code'];
  let sentence = ['learning', ...fragment, 'is', 'fun']; // Change this line
  return sentence;
}

console.log(spreadOut());
```

3. **[Profile Lookup](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/profile-lookup)**
   
**Solution:**
 ```javascript
// Setup
const contacts = [
  {
    firstName: "Akira",
    lastName: "Laine",
    number: "0543236543",
    likes: ["Pizza", "Coding", "Brownie Points"],
  },
  {
    firstName: "Harry",
    lastName: "Potter",
    number: "0994372684",
    likes: ["Hogwarts", "Magic", "Hagrid"],
  },
  {
    firstName: "Sherlock",
    lastName: "Holmes",
    number: "0487345643",
    likes: ["Intriguing Cases", "Violin"],
  },
  {
    firstName: "Kristian",
    lastName: "Vos",
    number: "unknown",
    likes: ["JavaScript", "Gaming", "Foxes"],
  },
];

function lookUpProfile(name, prop) {
  // Only change code below this line
  for(let i = 0; i < contacts.length; i++){
    if(contacts[i].firstName === name){
      if(contacts[i].hasOwnProperty(prop)){
        return contacts[i][prop];
      }
      else{
        return "No such property";
      }
    }
  }
  return "No such contact";
  // Only change code above this line
}

lookUpProfile("Akira", "likes");
```

4. **[Write Reusable JavaScript with Functions](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/write-reusable-javascript-with-functions)**

   ```javascript
    function reusableFunction (){
      console.log("Hi World");
    }

    reusableFunction()
   ```

5. **[Understanding Undefined Value returned from a Function](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/understanding-undefined-value-returned-from-a-function)**

```javascript
// Setup
let sum = 0;

function addThree() {
  sum = sum + 3;
}

// Only change code below this line

function addFive(){
  sum = sum + 5;
}

// Only change code above this line

addThree();
addFive();
```

6. **[Return a Value from a Function with Return](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/return-a-value-from-a-function-with-return)**

```javascript
function timesFive(x){
  return x *= 5;
}

timesFive(3);
```
