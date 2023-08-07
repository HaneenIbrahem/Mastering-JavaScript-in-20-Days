# Day 1: JavaScript: From First Steps to Professional
This README file summarizes the JavaScript lesson on intoduction and DOM. What is JS?, Where can write JS?, What is DOM?, Exercises.

## Lesson Summary
JavaScript: Language that modify and interact with HTML.
HTML: For content and structure.

We can write JS in:
- The browser's JS console.
- Local text file in editor, eg: VS Code.
- Online playground, eg: CodeSandbox.
_____________________________________________________________
DOM: Document Object Model
A simple document contain 
- html 
- head 
- body 
- header 
- div  ...

document.title: the title of the document.
document.body: the body element of the html.
document.body.children: all element within the body (header + div ...)

MDN: Mozilla Developer Network.

## Exercise 1:
1. All the p elements: 
   document.getElementByTagName("p")
2. The text "X": 
   document.querySelector("#p1-sympol").textContent;
   document.getElementById("p1-sympol").textContent;
3. The number of the squares in the board: 
   document.querySelectorAll(".square").length;
4. The text "A game you know": 
   document.querySelector("h2").textContent;
##
Editing the DOM with JS:
- textContent: eg: document.getElementById("player1")
- append: add on the text

## Exercise 2:
1. Change the player names
   document.querySelector("#p1-player").textContent = "Haneen"
   document.querySelector("#p2-player").textContent = "Hanaa"
2. Swap the player symbols
   document.getElementById("p1-sympol").textContent = "O"
   document.getElementById("p2-sympol").textContent = "X"
3. Change subtitle to "A game you know and love"
   document.querySelector("header h2").textContent = "A game you know and love"
   document.getElementByTagName("h2").append = "A game you know and love"


**querySelector with # : looking for the element not the ID**


## Coding Examples

**[Compound Assignment With Augmented Multiplication](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/compound-assignment-with-augmented-multiplication)**
**Solution:** 
let a = 5;
let b = 12;
let c = 4.6;

// Only change code below this line
a *= 5;
b *= 3;
c *= 10;

**[Concatenating Strings with the Plus Equals Operator](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/concatenating-strings-with-the-plus-equals-operator)**
**Solution:**
let myStr = "This is the first sentence. ";
myStr += "This is the second sentence.";

console.log(myStr);

**[Use Bracket Notation to Find the Nth-to-Last Character in a String](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures/basic-javascript/use-bracket-notation-to-find-the-nth-to-last-character-in-a-string)**
**Solution:**
// Setup
const lastName = "Lovelace";

// Only change code below this line
const secondToLastLetterOfLastName = lastName[lastName.length - 2]; // Change this line

console.log(secondToLastLetterOfLastName)
