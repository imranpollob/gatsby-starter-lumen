---
template: post
title: JavaScript variables
slug: javascript-variables
draft: false
date: 2019-08-13T13:12:31.721Z
description: 'Variable declaration using var, let and const'
category: JavaScript
tags:
  - javascript
---
* A variable is a literal assigned to an identifier, so you can reference and use.
* Variables in JavaScript do not have any type attached. Once you assign a specific literal type to a variable, you can later reassign the variable to any other type, without type errors or any issue.
* A variable must be declared before you can use it. There are 3 ways to do this, using var, let or const, and their purpose are different from each other.

### var

* Until ES2015, var was the only construct available for defining variables.


```
var a = 0
```

* If you forget to add var then, in modern environments, with strict mode enabled, you will get an error. In older environments (or with strict mode disabled) this will simply initialize the variable and assign it to the global object.
* If you don't initialize the variable when you declare it, it will have the undefined value until you assign a value to it.


```
var a //typeof a === 'undefined'
```

* You can re-declare the variable many times, overriding it:


```
var a = 1
var a = [1,2]
```

* You can also declare multiple variables at once in the same statement:


```
var a = 1, b = 2
```

* **The scope is the portion of code where the variable is visible.**
* A variable initialized with **var** **outside of any function is assigned to the global object**, has a global scope and is visible everywhere. 
* A variable initialized with **var** **inside a function is assigned to that function**, it's local and is visible only inside it, just like a function parameter.
* Any variable defined in a function with the same name as a global variable takes precedence over the global variable, shadowing it.
* **A block (identified by a pair of curly braces) does not define a new scope. A new scope is only created when a function is created, because var does not have block scope, but function scope.**
* Inside a function, any variable defined in it is visible throughout all the function code, **even if the variable is declared at the end of the function** it can still be referenced in the beginning, because JavaScript before executing the code actually moves all variables on top (something that is called **hoisting**). To avoid confusion, always declare variables at the beginning of a function.

### let

* let is a new feature introduced in ES2015 and it's essentially a **block scoped version of var**. Its scope is limited to the block, statement or expression where it's defined, and all the contained inner blocks.
* **Defining let outside of any function - contrary to var - does not create a global variable.**

Modern JavaScript developers might choose to only use let and completely discard the use of var.

### const

* Variables declared with var or let can be changed later on in the program, and reassigned. Once a const is initialized, it's value can never be changed again, and it **can't be reassigned to a different value**.


```
const a = 'Imran Pollob'
```

* const has **block scope**, same as let
* We can't assign a different literal to the a const however, **can mutate it**, if it's an object that provides methods that mutate its contents. const does not provide immutability, just makes sure that the reference can't be changed.

```
// We can create a const object:
const car = {type:"Fiat", model:"500", color:"white"};

// We can change a property:
car.color = "red";

// We can add a property:
car.owner = "Johnson";

car = {type:"Volvo", model:"EX60", color:"red"};    // ERROR

// We can create a constant array:
const cars = ["Saab", "Volvo", "BMW"];

// We can change an element:
cars[0] = "Toyota";

// We can add an element:
cars.push("Audi");

cars = ["Toyota", "Volvo", "Audi"];    // ERROR
```

Modern JavaScript developers might choose to always use const for variables that don't need to be reassigned later in the program.
