---
title: "JS Required Params"
date: 2018-03-18T10:54:58+02:00
draft: false
description: Enforcing Required Parameters in JavaScript using ES6
tags: [JS, JavaScript, es6, arguments, parameters, es6-tricks]
keywords: [JS, JavaScript, ES6, arguments, parameters, ES6 tricks]
---
TBH, JavaScript isn't my favorite coding language. Luckily, ECMAScript 2015 (ES6) added some really useful tricks.

Several languages support the option of enforcing required function arguments. Meaning the program
will throw an exception when the function is called without these parameters.

Here is a suggestion for implementing this, using ES6 [default parameters](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters).

Say we have our `multiply` function:
```JS
const multiply = (a, b) => a * b;
```

We can declare a simple `required` function:
```JS
const required = () => { throw new Error('Missing required parameter') };
```

And add it to `multiply`'s arguments as a default parameter:
```JS
const multiply = (a = required(), b = required()) => a * b;
```

Calling `multiply(3)` will result in:    
`Error: Missing required parameter`

![ES6 evolution](/images/es6.png)
