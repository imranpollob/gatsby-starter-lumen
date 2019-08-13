---
template: post
title: Arrow Functons / F!t Arrow
slug: arrow-functions-f!t-arrow
draft: true
date: 2019-08-13T20:57:54.046Z
description: Learn about the most welcoming JavaScript
category: JavaScript
tags:
  - javascript
---
Arrow functions
- Most impactful change in ES6/ES2015 and since their introduction they changed forever how JavaScript code looks (and works).

```
const myFunction = function() { //...
}
// Arrow function
const myFunction = () => { 
//...
}
```

- If the function body contains just a single statement, you can omit the brackets and write all on a single line:
```
const myFunction = () => doSomething()
```

- Parameters are passed in the parentheses: 
```const myFunction = (param1, param2) => doSomething(param1, param2)
```

- If you have one (and just one) parameter, you could omit the parentheses completely: 
```
const myFunction = param => doSomething(param)
```

Thanks to this short syntax, arrow functions encourage the use of small functions. Implicit return 21Arrow functions
Arrow functions allow you to have an implicit return: values are returned without having to use
the return keyword.
It works when there is a one-line statement in the function body:
const myFunction = () => 'test'
myFunction() //'test'
Another example, when returning an object, remember to wrap the curly brackets in
parentheses to avoid it being considered the wrapping function body brackets:
const myFunction = () => ({ value: 'test' })
myFunction() //{value: 'test'}
How this works in arrow functions
this is a concept that can be complicated to grasp, as it varies a lot depending on the
context and also varies depending on the mode of JavaScript (strict mode or not).
It's important to clarify this concept because arrow functions behave very differently compared
to regular functions.
When defined as a method of an object, in a regular function this refers to the object, so you
can do:
const car = {
model: 'Fiesta',
manufacturer: 'Ford',
fullName: function() {
return `${this.manufacturer} ${this.model}`
}
}
calling car.fullName() will return "Ford Fiesta" .
The this scope with arrow functions is inherited from the execution context. An arrow
function does not bind this at all, so its value will be looked up in the call stack, so in this
code car.fullName() will not work, and will return the string "undefined undefined" :
const car = {
model: 'Fiesta',
manufacturer: 'Ford',
fullName: () => {
22Arrow functions return `${this.manufacturer} ${this.model}` } } Due to this, arrow functions are not suited as object methods.
Arrow functions cannot be used as constructors either, when instantiating an object will raise a TypeError .
This is where regular functions should be used instead, when dynamic context is not needed.
This is also a problem when handling events. DOM Event listeners set this to be the target element, and if you rely on this in an event handler, a regular function is necessary:
const link = document.querySelector('#link') link.addEventListener('click', () => { // this === window
})
const link = document.querySelector('#link') link.addEventListener('click', function() { // this === link
})
