# Day 12: Deep JavaScript Foundations, v3
This README file summarizes the JavaScript lesson on Equality and Static Typing

## Lesson Summary

**Equality**

`==` (loose equality or Coercive Equality): performs type coercion before comparison.
`===` (strict equality): compares values without type coercion and checks both values and data types.
```JavaScript
const num = 42;
const str = "42";

console.log(num == str); // true (loose equality)
console.log(num === str); // false (strict equality)
```

1. If both values have the same type, compare them directly.
	- If they are equal, return true.
	- If they are not equal, return false.

2. If one of the values is null and the other is undefined, return true.

3. If one of the values is a number and the other is a string, convert the string to a number and compare them.

4. If one of the values is a boolean, convert it to a number (true becomes 1, false becomes 0) and compare with the other value.

5. If one of the values is an object and the other is a primitive, convert the object to a primitive using the valueOf and toString methods (in that order) and compare with the primitive value.

6. If none of the above cases apply, return false.
```javascript
console.log(5 == "5");        // true (coerces string "5" to number 5)
console.log(null == undefined); // true (special case)
console.log(true == 1);       // true (coerces boolean true to number 1)
console.log({} == "[object Object]"); // true (coerces object to string "[object Object]")
console.log([1] == 1);        // true (coerces array to primitive)
```

**Double equals walkthrough:**
**5 == "5"**

1. Check if both values have the same type. In this case, one is a number (5) and the other is a string ("5"). They have different types.

2. Check if one of the values is null and the other is undefined. This is not the case.

3. Check if one of the values is a number and the other is a string. Convert the string to a number and compare:

	- Convert "5" to a number. It becomes 5.
	- Compare 5 (number) with 5 (number).
	
4. Since both values are now numbers and have the same value (5), the comparison returns **true**.

**Double equals corner cases:**
```javascript
0 == false;  // true
"" == false; // true
null == undefined; // true
5 == "5";    // true
1 == true;   // true
[1, 2] == "1,2"; // true
NaN == NaN;  // false
false == null;      // false
false == undefined; // false
0 == null;          // false
0 == undefined;     // false
0 == "";    // true
false == ""; // true
```

corner cases: Booleans
```JavaScript
true == 1;    // true
false == 0;   // true

true == "true";   // false
false == "";      // true

true == null;       // false
false == undefined; // false

true == {};      // false
false == [];     // true

true == NaN;    // false
false == NaN;   // false

true == "1";    // true
false == "0";   // true

```

**== Summary: 
If the types are the same: ===
If null or undefined: equal 
If non-primitives: ToPrimitive 
Prefer: ToNumber**

----------
**Static Typing**

Static typing is a programming language feature that requires variables to be explicitly declared with a data type at compile-time, This means that once a variable is assigned a specific data type, it cannot be changed to another data type during the program's execution.

Languages with static typing include TypeScript, Java, C++, and C#. In these languages, the data type of a variable is determined when the variable is declared, and the compiler checks whether the variable is used consistently with its declared type. If there's a type mismatch, the compiler generates an error before the program is executed.

Languages like JavaScript traditionally use dynamic typing, where variable types can change at runtime. However, tools like TypeScript provide optional static typing features that allow developers to enjoy some of the benefits of static typing while still working within a dynamically typed language.

**TypeScript** is a superset of JavaScript that adds optional static typing to the language.

**Flow** is a static type checker developed by Facebook for JavaScript. It aims to provide gradual typing, allowing developers to introduce type annotations incrementally to existing JavaScript codebases.

Comparison:

TypeScript provides a more feature-rich and expressive type system compared to Flow.
TypeScript has a larger community and ecosystem, with extensive documentation, third-party libraries, and tools.
Flow's gradual typing approach makes it suitable for projects with existing JavaScript codebases that want to introduce type checking incrementally.
Both TypeScript and Flow improve code quality, reduce runtime errors, and enhance developer productivity.


TypeScript/Flow: Pros: 

1. They make types more obvious in code.
2. Familiarity: they look like other language's type systems.
3. Extremely popular these days.
4. They're very sophisticated and good at what they do.

Cons:

1. They use "non-JS-standard" syntax (or code comments).
2. They require a build process, which raises the barrier to entry.
3. Their sophistication can be intimidating to those without prior formal. types experience.
4. They focus more on "static types" (variables, parameters, returns, properties, etc) than value types.
5. The only way to have confidence over the runtime behavior is to limit/eliminate dynamic typing.

**Inferencing** feature in programming languages that allows the compiler or interpreter to automatically deduce the data types of variables and expressions based on their usage in the code, without the need for explicit type annotations.

Custom Types:

1. Interfaces
2. Type Aliases
3. Classes
4. Enums


## DELIEVERABLES:

1. **[Question 1:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%202/tasks.md#question-1)**
   
**Solution:** 
 ```javascript

```

2. **[Question 2:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%202/tasks.md#question-2)**
   
**Solution:**

1. Variable `a` is declared using var, which has function scope. This means it's accessible throughout the entire function. Therefore, it will have a value of 1 and will be logged as 1.
2. Variable `b` is declared using let and has block scope. It's only accessible within the if block. When you try to log b outside the block using `console.log(b)`, it results in a ReferenceError because b is not defined in that scope.
3. Variable `c` is declared using const and also has block scope. Similar to b, it's only accessible within the if block. Attempting to log c outside the block using `console.log(c)` would also result in a ReferenceError.

So, the correct output is: C

3. **[Question 3:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%202/tasks.md#question-3)**
   
**Solution:**

1. Variable `a` is declared using var and is function-scoped. However, it's declared after the first `console.log(a)`. Due to hoisting, `a` is initialized with undefined at the beginning of the function scope, so `console.log(a)` will log `undefined`.
2. Variable `b` is declared using let and has block scope. It's not declared before the first `console.log(b)`, so attempting to log `b` will result in a `ReferenceError`.
3. Variable `c` is declared using const and also has block scope. Like b, it's not declared before the first `console.log(c)`, so attempting to log `c` will result in a `ReferenceError`.

So, the correct output is: A

4. **[Question 4:](https://github.com/orjwan-alrajaby/gsg-QA-Nablus-training-2023/blob/main/learning-sprint-1/week3%20-%20deep-javascript-foundations-v3/day%202/tasks.md#question-4)**
   
**Solution:**

1. The first `console.log` outputs `[ 36, 100, 45 ]`.
2. An `if` block is entered (always true): New block-scoped variables are declared: `a = 1`,` b = 2`,` c = 3`.
3. The second `console.log` inside the if block outputs `[ 1, 2, 3 ]`.
4. The `if` block is exited: The original `var a` value is changed to `1`, but the `let b` and `const c` values remain unchanged.
5. The third `console.log` outside the `if` block outputs `[ 1, 100, 45 ]`.

So, the correct choice is:
C) [ 36, 100, 45 ] | [ 1, 2, 3 ] | [ 1, 100, 45 ]
