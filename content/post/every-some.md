---
title: "every() day some() time"
date: 2018-02-15T17:43:17+02:00
draft: false
description: JavaScript Array every() and some()
tags: ["JS", "JavaScript", "array", "every", "some", "methods"]
keywords: [JS, JavaScript, array, every, some, methods]
---
Moving from Python to JavaScript, I often find myself thinking _what's the equivalent of X in JS?_

![Python vs JS](/images/python-js.jpg)

Two nifty-little-tricks I use regularly are Python's built-in functions: [`any()`](https://docs.python.org/2/library/functions.html#any) and [`all()`](https://docs.python.org/2/library/functions.html#all).   
Both accept an iterable and return `True` if any/all element/s of the iterable are true, 'False' otherwise.

**_Today I learned_** their JS equivalent for arrays: [`some()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some) and [`every()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every).    
The function checks whether at least one/every element in the array passes the condition implemented by the provided callback.

#### Usage
```JavaScript
[10, 11, 12, 13].every((x) => x > 10); // false
```

```JavaScript
[8, 9, 10, 11].some((x) => x > 10); // true
```

* The 2nd callback parameter (optional) is the element index
* The 3rd (optional as well) is the array called
