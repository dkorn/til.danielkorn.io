---
title: "JS Named Parameters"
date: 2018-06-24T23:38:21+03:00
draft: false
description: Using ES6 to achieve named arguments in Javascript
tags: [destructuring, JS, JavaScript, es6, arguments, parameters, es6-tricks]
keywords: [destructuring, JS, JavaScript, ES6, arguments, parameters, ES6 tricks]
---
Let me start with an apology for the title, which is a bit inaccurate.
There are no native named parameters in Javascript.

Having said that, using ES6 awesome destructuring we can enact named parameters.

Now before demonstrating exactly how, I want to give two use cases where it can come in handy.

* The first scenario is when we have complex function calls, with several arguments in different
types. This makes the call less readable therefore more bug-prone (missing parameter, wrong order and
more).

* The second is when dealing with a promise. You can define explicitly what you're expecting to
  receive and even set up default values. 

#### Usage
Before a function is executed all arguments passed are assigned to parameters based on its'
signature. That means object destructuring will perfectly here.

Instead of:
```JS
const myFunc = (organizationId, name, force, verbose) => {
  ...
}

// not the most readable function call somewhere in your code
myFunc(17, 'Test', true, false)
```
You can do this:

```JS
const myFunc = ({ organizationId, name, force, verbose }) => {
  ...
}

// not the most readable function call somewhere in your code
myFunc({ organizationId: 17, name: 'Test', force: true, verbose: false })
```

![Say my name gif](https://media1.tenor.com/images/59ebfec80b12c36e475786a3efea3655/tenor.gif?itemid=8142083)

The important thing to remember is that destructuring is based on same property name. The order
does not matter.

#### Pro Tips

* Like regular destructuring, you can also rename the parameters during the assignment:

```JS
// renamed name to orgName
const myFunc = ({ orgId, name: orgName , force, verbose }) => {
  console.log(orgName); // 'Test'
}

myFunc({ orgId: 17, name: 'Test', force: true, verbose: false)
```

* We can have default values and optional parameters

```JS
const myOtherFunc = ({ x = 1, y = 2, z = 3 } = {}) => {
  console.log(x, y, z); 
}

// x isn't passed thus received its default value
myOtherFunc({ y: 5, z: 10}) // 1 5 10
```

