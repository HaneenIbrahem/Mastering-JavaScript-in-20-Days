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

##
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


## DELIEVERABLES:

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

