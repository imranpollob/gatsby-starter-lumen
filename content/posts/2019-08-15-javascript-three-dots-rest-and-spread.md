---
template: post
title: 'JavaScript three dots (...) Rest and Spread '
slug: javascript-three-dots-rest-and-spread
draft: false
date: 2019-08-15T10:53:24.752Z
description: Work with array and object in modern way
category: Javascript
tags:
  - javascript
---
* You can expand an array, an object or a string using the spread operator (...). Let's start with an array example. Given


```
const a = [1, 2, 3]
```

* You can create a new array using


```
const b = [...a, 4, 5, 6]
```

* You can also create a copy of an array using


```
const c = [...a]
```

* This works for objects as well. Clone an object with:


```
const newObj = { ...oldObj }
```

* Using strings, the spread operator creates an array with each char in the string:


```
const hey = 'hey'
const hiArray = [...hey] // ['h', 'e', 'y']
```

* This operator has some pretty useful applications. The most important one is the ability to use an array as function argument in a very simple way:


```
const f = (foo, bar) => {}
const a = \[1, 2]
f(...a)
Math.max(...a) // 3
```

(in the past you could do this using f.apply(null, a) but that's not as nice and readable)

* Array Destructuring:


```
const numbers = [1, 2, 3, 4, 5]
[first, second, ...others] = numbers
```

* Spread Elements:


```
const numbers = \[1, 2, 3, 4, 5]
const sum = (a, b, c, d, e) => a + b + c + d + e
const sum = sum(...numbers)
```

ES2018 introduces rest properties, which are the same but for objects.

* Rest properties:


```
const { first, second, ...others } = {
first: 1,
second: 2,
third: 3,
fourth: 4,
fifth: 5
} 
first // 1
second // 2
others // { third: 3, fourth: 4, fifth: 5 }
```

* Spread properties allow to create a new object by combining the properties of the object
  passed after the spread operator:


```
const items = { first, second, ...others }
items //{ first: 1, second: 2, third: 3, fourth: 4, fifth: 5 }
```

* There is also a special array-like object named arguments that contains all arguments by their index. When rest parameters did not exist in the language, and using arguments was the only way to get all arguments of the function.


```
function show() {
  console.log( arguments.length ); // 4
}

show(1,2,3,4);
```

Notes:

* Arrow function doesn't have own `arguments`, it takes them from the outer “normal” function.
* When ... is at the end of function parameters, it’s “rest parameters” and gathers the rest of the list of arguments into an array.
* When ... occurs in a function call or alike, it’s called a “spread operator” and expands an array into a list.
