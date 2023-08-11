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

| Strict |             | loosy goosy |

| === |                  | == |            | => equals |

| !== |                  | != |            | => does not equal |


1 === 1       => 

1 == 1        =>

"1" === "1"   =>

"1" == "1"    =>

1 === "1"     =>

1 == "1"      =>

##
Editing the DOM with JS:
- textContent: eg: document.getElementById("player1")
- append: add on the text

## Exercise 2:
1. Change the player names:
   ```javascript
   document.querySelector("#p1-player").textContent = "Haneen"
   document.querySelector("#p2-player").textContent = "Hanaa"
2. Swap the player symbols:
   ```javascript
   document.getElementById("p1-sympol").textContent = "O"
   document.getElementById("p2-sympol").textContent = "X"
4. Change subtitle to "A game you know and love":
   ```javascript
   document.querySelector("header h2").textContent = "A game you know and love"
   document.getElementByTagName("h2").append = "A game you know and love"


**querySelector with # : looking for the element not the ID**


## Coding Examples

1. **[Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)**
   
**Solution:** 
 ```javascript
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;
```

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
