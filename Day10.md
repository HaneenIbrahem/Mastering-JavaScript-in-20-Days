# Day 9: JavaScript: The Hard Parts, v2
This README file summarizes the JavaScript lesson on Classes & Prototypes (OOP).

## Lesson Summary

**Classes, Prototypes - Object Oriented JavaScript:**

These concepts are at the core of JavaScript's OOP model. They provide ways to create and structure objects, encapsulate behavior, and establish relationships between objects through inheritance. Classes, prototypes, and inheritance are essential tools for building robust and maintainable JavaScript applications.

**- An enormously popular paradigm for structuring our complex code**

difference between `__proto__` and `prototype`

-  `__proto__` :
1. is an internal property of an object that refers to its prototype.
2. allowing an object to inherit properties and methods from its prototype.
3. ` __proto__` is widely supported in browsers

`prototype` :
1. is a property of constructor functions. When you create an object using a constructor function with the `new` keyword, the object's prototype is set to the constructor's prototype.
2. used to define properties and methods that will be shared among instances created by the constructor function.

**The `new` and `class` keywords as tools to automate our object & method creation**

The Object-oriented paradigm aims is to let us achieve these three goals: 
1. Easy to reason about
2. Easy to add features to (new functionality)
3. Nevertheless efficient and performant
-----------

if we want to create a user for example :
```JavaScript
const user1 = {
 name: "Will",
 score: 3,
 increment: function() { user1.score++; }
};
user1.increment(); //user1.score -> 4
```
what if we have millions of users!!

**Solution 1: . Generate objects using a function**
```JavaScript
function userCreator(name, score) {
 const newUser = {};
 newUser.name = name;
 newUser.score = score;
 newUser.increment = function() {
 newUser.score++;
 };
 return newUser;
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment()
```

**Problems:** Each time we create a new user we make space in our computer's 
memory for all our data and functions. But our functions are just copies

**Benefits:** It's simple and easy to reason about!
 
 
**Solution 2: Using the prototype chain**
```JavaScript
function userCreator (name, score) {
 const newUser = Object.create(userFunctionStore);
 newUser.name = name;
 newUser.score = score;
 return newUser;
};
const userFunctionStore = {
 increment: function(){this.score++;},
 login: function(){console.log("Logged in");}
};
const user1 = userCreator("Will", 3);
const user2 = userCreator("Tim", 5);
user1.increment();
```
**hasOwnProperty method:** is a built-in method in JavaScript that is available on all objects. It is used to check if an object has a specific property. This method is used to distinguish between properties that are directly defined on an object and properties that are inherited from its prototype chain.

**Problems:** No problems! It's beautiful. Maybe a little long-winded

**Benefits:** Super sophisticated but not standard

**Solution 3 - Introducing the keyword that automates 
the hard work: new**

```JavaScript
function userCreator(name, score){
 this.name = name;
 this.score = score;
}
userCreator.prototype.increment = function(){ this.score++; };
userCreator.prototype.login = function(){ console.log("login"); };
const user1 = new userCreator(“Eva”, 9)
user1.increment()
```

**Benefits: **
Faster to write. Often used in practice in professional code
**Problems: **
95% of developers have no idea how it works and therefore fail interviews
We have to upper case first letter of the function so we know it requires `new` to work

**Solution 4: The class ‘syntactic sugar’**
```JavaScript

class UserCreator {
 constructor (name, score){
 this.name = name;
 this.score = score;
 }
 increment (){ this.score++; }
 login (){ console.log("login"); }
}
const user1 = new UserCreator("Eva", 9);
user1.increment();
```

**Benefits: **
Emerging as a new standard
Feels more like style of other languages (e.g. Python)
**Problems: **
99% of developers have no idea how it works.

## DELIEVERABLES:
