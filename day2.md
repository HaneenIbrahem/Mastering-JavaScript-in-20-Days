# Day 2: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on Values & Data Types, Operators and Expressions.

## Lesson Summary
typeof "42" = String

typeof 42 = Number

**Data types**
- String
- Boolean
- Null
- Number
- Undefined

**JS has 2 kinds of data :**
1. Primitive types (Strings, Numbers)
2. Objects (Document)


## Exercise 1: Which data type is each of these values?

1. false -> boolean
2. "true" -> string
3. document.title -> string
4. "some string".length -> number
5. null -> object

## Exercise 2: 

1. Add your last name in the players listing:
   ```javascript
   document.getElementById("p1-name").append(" Ibrahem");
   document.querySelector("#p1-name").textContent = "Haneen Ibrahem";
   ```

2. Retrive the first "T" in the page title:
   ```javascript
   document.title[9];
   ```

3. Answer whether the page title contains the string "JavaScript":
   ```javascript
   document.title.includes("JavaScript");
   ```

4. capitalize the heading "Tic Tac Toe":
   ```javascript
   document.querySelector("header h1").textContent.toUpperCase;
   document.querySelector("header h1").style.textTransform = "uppercase";
   ```
##

**Operations**

Arithmatic operations:
(+, -, *, /)

Comparison operations:
(>, <, >=, <=)

Logical operations:
(&&, ||, !)


| Strict | Loosy Goosy | Description        |
| ------ | ------------ | ------------------ |
| ===    | ==           | Equals             |
| !==    | !=           | Does not equal     |


1 === 1       =>  ✅

1 == 1        =>  ✅

"1" === "1"   =>  ✅

"1" == "1"    =>  ✅

1 === "1"     =>  ❎

1 == "1"      =>  ✅

##

let : to declare a variable, can be changed
const: declare constant, can't be changed

**Note:** popular way to declare variables is using camelCase.

Statement: tell js to do something (declare, assign a variable).

Expressions: asks js for a value.


## DELIEVERABLES:

1. **[QUESTION #1](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%202/tasks.md#question-1)**

**Solution:** 

- console.log(a == b);

Output: true

Explanation: `==` converts one or both operands to the same type before making the comparison

- console.log(b === c);
  
Output: false

Explanation: `===` performs a strict equality comparison without type coercion.

- console.log(!!d);
  
Output: true

Explanation: The first ! operator negates the truthiness of the value, and the second ! operator negates it again


2. **[Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)**
   
**Solution:**
 ```javascript
let myStr = "This is the first sentence. ";
myStr += "This is the second sentence.";

console.log(myStr);
```

3. **[Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)**
   
**Solution:**
 ```javascript
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length - 2]; // Change this line

console.log(secondToLastLetterOfLastName)
```
