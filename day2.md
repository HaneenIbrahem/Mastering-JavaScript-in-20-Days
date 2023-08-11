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


2. **[QUESTION #2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%202/tasks.md#question-2))**
   
**Solution:**

console.log(4 + 5 * "7");

The multiplication operation `5 * "7"` is evaluated first, it attempts to convert the string to a number and performs the multiplication, 5*7 = 35. The addition operation 4 + 35 is performed. Both operands are numbers (4 and 35), so the + operator performs addition. The result of 4 + 35 is 35.

Final Output:
The output of the console.log statement will be 39.


3. **[QUESTION #3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%202/tasks.md#question-3)**
   
**Solution:**

let result = 5 + 2 * 3 - 1;

2 * 3 is evaluated first. In JavaScript, the * operator has higher precedence than the + and - operators. 
so the result is 6.
then the expression becomes 5 + 6, which is straightforward. The result of 5 + 6 is 11.
Finally, the expression becomes 11 - 1, which is also straightforward. The result of 11 - 1 is 10.

4. **[QUESTION #4:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%202/tasks.md#question-4)**
   
**Solution:**

- console.log(x == y);

Output: true

Explanation: The == operator converts one or both operands to the same type before making the comparison. Since the number 10 and the string '10' have the same value, the comparison x == y evaluates to true.

- console.log(x === y);
  
Output: false

Explanation: === Unlike ==, it does not perform type coercion. It checks both value and type, meaning both operands must be of the same type and have the same value for the comparison to evaluate to true
In this case, x is a number (10) and y is a string ('10'), and their types are different. so x === y evaluates to false.

5. **[QUESTION #5:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week1%20-%20javascript-from-first-steps-to-professional/day%202/tasks.md#question-5)**

- num > 10: in this case it is 15 > 10 which is true
- isPositive: This is a boolean variable with the value true, so it directly evaluates to true.
- (num > 10 && isPositive): the logical AND (&&) operator returns true.
- num < 0: 15" is not less than 0, so this part of the expression evaluates to false.
- (num > 10 && isPositive) || num < 0: one side of the OR operator is true (num > 10 && isPositive) and the other side is false (num < 0), the OR operator returns true.
- result = (num > 10 && isPositive) || num < 0: Finally, the result of the entire expression is true.

Final Output:

The value of the variable result is true.

