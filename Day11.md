# Day 11: Deep JavaScript Foundations, v3
This README file summarizes the JavaScript lesson on intoduction Types Coercion and Philosophy of Coercion.

## Lesson Summary

**Types:** there are two main categories of data types:
1. Primitive 
2. Non-primitive (Reference)

**Primitive Types:**
1. Undefined: Represents a variable that has been declared but has not been assigned a value yet.
2. Null
3. Boolean: true or false.
4. Number: numeric values
5. String: sequences of characters
6. Symbol: Introduced in ECMAScript 6 (ES6), represents a unique and immutable value often used as object property keys.
7. BigInt: introduced in ECMAScript 2020 (ES11)

```JavaScript
let num = 42;        // Number
let str = "Hello";   // String
let bool = true;     // Boolean
let undef;           // Undefined
let n = null;        // Null
let sym = Symbol();  // Symbol
```

**Reference Types:**
1. Object
2. Array
3. Function

```JavaScript
let obj = { key: "value" };  // Object
let arr = [1, 2, 3];         // Array
function myFunction() {}     // Function

let newObj = obj;            // Both newObj and obj reference the same object
```

**typeof:** used to determine the data type of a given expression or value.

typeof operator can return:
- "undefined": If the value is undefined.
- "boolean": If the value is a boolean.
- "number": If the value is a number (including NaN and Infinity).
- "string": If the value is a string.
- "bigint": If the value is a BigInt.
- "symbol": If the value is a Symbol.
- "function": If the value is a function.
- "object": If the value is an object or null.

```JavaScript
console.log(typeof undefined);  // "undefined"
console.log(typeof true);       // "boolean"
console.log(typeof 42);         // "number"
console.log(typeof "hello");    // "string"
console.log(typeof null);       // "object"
console.log(typeof function(){});  // "function"
console.log(typeof {});         // "object"
console.log(typeof []);         // "object"
console.log(typeof Symbol());   // "symbol"
console.log(typeof BigInt(123)); // "bigint"
```

**Undefined vs. Undeclared vs. Uninitialized **

Undefined: A variable that has been declared but hasn't been assigned a value
```JavaScript
let x;
console.log(x); // Output: undefined
```

Undeclared: A variable that has not been declared using the var, let, or const keyword before being used.
```JavaScript
console.log(y); // ReferenceError: y is not defined
```

Uninitialized: A variable exists but is not yet initialized with a value.
```JavaScript
console.log(z); // ReferenceError: Cannot access 'z' before initialization
let z = 10;
```


**BigInt:**
```JavaScript
const bigInt1 = 1234567890123456789012345678901234567890n;
const bigInt2 = BigInt("9876543210987654321098765432109876543210");

const sum = bigInt1 + bigInt2;
console.log(sum); // Outputs: 11111111101111111110111111111101111111100n
```

**kinds of emptiness**
1. Undefined
2. Null
3. Empty String
4. NaN (Not-a-Number)
5. Empty Arrays and Objects
6. Falsy Values

**NaN and isNaN**

NaN:  It is a special value in JavaScript that represents the result of an arithmetic operation that cannot be expressed as a valid number.
```JavaScreipt
const result = 0 / 0; // NaN
const invalidNumber = Number("abc"); // NaN
```
isNaN: is a built-in JavaScript function that checks if a given value is NaN. It returns true if the value is NaN, and false if the value is a valid number.
```JavaScript
isNaN(NaN); // true
isNaN(123); // false
isNaN("456"); // false
isNaN("abc"); // true
```

**Important to note that isNaN() also coerces non-number values to numbers before checking for NaN.**
```JavaScript
isNaN("123"); // false, because "123" is coerced to the number 123
isNaN("abc"); // true, because "abc" cannot be coerced to a number
```
**To avoid this coercion behavior, you can use Number.isNaN():**
```JavaScript
Number.isNaN(NaN); // true
Number.isNaN("123"); // false
Number.isNaN("abc"); // false
```

**negative zero** 
In JavaScript, positive zero and negative zero are considered to be equal in terms of comparison:
```JavaScript
+0 === -0; // true
-0 < +0;   // false
+0 < -0;   // false
```
Division by Zero:
```JavaScript
1 / +0; // Infinity
1 / -0; // -Infinity
```

Fundamental Objects
**Built-In Objects **
**Native Functions**

Use new:
- Object() 
- Array() 
- Function() 
- Date() 
- RegExp() 
- Error()

Don't use new:
1. String() 
2. Number() 
3. Boolean()
-------------
**Coercion:**
Coercion in JavaScript refers to the automatic or implicit conversion of one data type to another.

**There are two types of coercion in JavaScript: implicit coercion and explicit coercion.**
1. Implicit Coercion:  happens automatically when values of different data types are used together in an operation. JavaScript tries to convert one or both of the values to a common data type before performing the operation. For example:
```JavaScript
var num = 5;
var str = "10";
console.log(num + str); // Result: "510" (string concatenation)
```
2. Explicit Coercion:  involves manually converting a value from one data type to another using built-in functions or operators. This is also known as type casting. For example:
```JavaScript
var str = "42";
var num = Number(str); // Explicitly convert string to number
console.log(num + 10); // Result: 52 (numeric addition)
```

Some common examples of abstract operations include:
1. ToPrimitive(input [, PreferredType]):
This abstract operation converts a given value to a primitive value. It takes an optional argument PreferredType that indicates whether the result should be converted to a string or a number.
2. ToNumber(argument):
This abstract operation converts its argument to a numeric value, following the rules for type coercion.
3. ToString(argument):
This abstract operation converts its argument to a string value, following the rules for type coercion.
4. ToBoolean(argument):
This abstract operation converts its argument to a Boolean value, following the rules for type coercion.
5 ToObject(argument):
This abstract operation converts its argument to an object, if it's not already an object.

**cases of coersion:**
1. String Concatenation:
```javascript
const num = 42;
const str = "Hello, " + num; // Coercion of num to a string
console.log(str); // "Hello, 42"
```
2. Arithmetic Operations:
```javascript
const strNum = "10";
const num = strNum * 2; // Coercion of strNum to a number
console.log(num); // 20
```
3. Comparison Operators:
```javascript
const num1 = 5;
const strNum = "5";
console.log(num1 == strNum); // Coercion and comparison, true
console.log(num1 === strNum); // Strict comparison, false
```
4. Truthy and Falsy Values:
```javascript
const falsyValue = ""; // Coercion to false
const truthyValue = "Hello"; // Coercion to true
```
5. Implicit String Conversion:
```javascript
const num = 42;
const str = num + ""; // Coercion of num to a string
console.log(str); // "42"
```
6. Implicit Boolean Conversion:
```javascript
const value = "hello";
if (value) {
  console.log("Value is truthy"); // Coercion of value to boolean
}
```
6. Using "+" with Different Types:
```javascript
const num = 42;
const str = "20";
const result = num + str; // Coercion of both values to strings and concatenation
console.log(result); // "4220"
```
7. Logical Operators:
```javascript
const num = 5;
const strNum = "10";
if (num > 3 && strNum > 8) {
  console.log("Both conditions are true");
}
```
8. Ternary Operator:
```javascript
const age = 18;
const message = age >= 18 ? "Adult" : "Minor"; // Coercion and conditional check
console.log(message); // "Adult"
```
9. Function Arguments:
```javascript
function greet(name) {
  console.log("Hello, " + name); // Coercion of name to a string
}
greet("Alice"); // "Hello, Alice"
```

**Boxing**
some examples of boxing in JavaScript:
1. Number Boxing:
```javascript
const num = 42;
const numObject = new Number(num); // Boxing: Wrapping primitive in Number object
console.log(numObject.toFixed(2)); // Using a method available on Number object
```
2. String Boxing:
```javascript
const str = "Hello";
const strObject = new String(str); // Boxing: Wrapping primitive in String object
console.log(strObject.length); // Using a property available on String object
```
3. Boolean Boxing:
```javascript
const bool = true;
const boolObject = new Boolean(bool); // Boxing: Wrapping primitive in Boolean object
console.log(boolObject.valueOf()); // Using a method available on Boolean object
```

Intentional coersion:
1. String to Number Conversion:
```javascript
const stringNumber = "42";
const numericValue = Number(stringNumber); // Intentional coercion
console.log(numericValue + 10); // 52 (numeric addition)
```
2. Number to String Conversion:
```javascript
const numericValue = 42;
const stringValue = String(numericValue); // Intentional coercion
console.log("The answer is: " + stringValue); // "The answer is: 42" (string concatenation)
```
3. Explicit Boolean Conversion:
```javascript
const truthyValue = "Hello";
const falseyValue = "";
const truthyBoolean = Boolean(truthyValue); // Intentional coercion
const falseyBoolean = Boolean(falseyValue); // Intentional coercion
console.log(truthyBoolean); // true
console.log(falseyBoolean); // false
```

**Useful: when the reader is focused on what's important
Dangerous: when the reader can't tell what will happen
Better: when the reader understands the code**

## DELIEVERABLES:

1. **[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%201/tasks.md#question-1)**
   
**Solution:** 
 ```javascript
function convertStringToNumber(input) {
  if (typeof input === 'string') {
  	let convertedNumber = + input;
	if(!isNaN(convertedNumber){
		return convertedNumber;
	}else{
		return {value: input, type: "string"};
	}
  }else{
  	return {value: input, type: typeof input};
  }
}
```

2. **[Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%201/tasks.md#question-2)**
   
**Solution:**
 ```javascript
const checkNaN = (value) => {
	return isNaN(value);
}
```

3. **[Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%201/tasks.md#question-3)**
   
**Solution:**
 ```javascript
function isEmptyValue(value) {
	return value === undefined || value === null || value === '';
}
```

4. **[Question 4:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%201/tasks.md#question-4)**
   
**Solution:**
 ```javascript
 function compareObjects(input1, input2) {
 let arr = [];
	if (typeof input1 === 'object' && typeof input2 === 'object') {
		return input1 === input2;
	}else{
		arr.push(input1);
		arr.push(input2);
		return arr;
	}
}
```

5. **[Question 5:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%201/tasks.md#question-5)**
   
**Solution:**
 ```javascript
const complexCoercion = (input) => {
	if(typeof input !== "object" && typeof input !== "function"){
		if(typeof input === "number"){
			return Boolean(input.toString());
		}else if(typeof input === "string"){
			return Boolean(input);
		}else if(input === null || typeof input === "undefined"){
			return false;
		}
	}else{
	return input;
	}
}
```
