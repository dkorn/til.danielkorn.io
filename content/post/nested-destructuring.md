---
title: "Nested Destructuring"
date: 2019-01-10T18:33:05+02:00
draft: false
images: [/images/es6.jpg]
description: ES6 Destructuring for nested objects
tags: [destructuring, JS, JavaScript, es6, nested, objects, es6-tricks]
keywords: [destructuring, JS, JavaScript, ES6, Nested, Objects, ES6 tricks]
---

Object destructuring is probably my favorite ES6 feature.

I've already written a [post](https://danielkorn.io/post/named-parameters/) explaining how to achieve named arguments
using ES6 destructuring.

Today, while code reviewing with [Oron](https://github.com/oronsh), I learned how to destruct nested
objects.

### Example

Let's say we have a user object and we want to get its' name:

```
const user = {
  id: 17,
  name: 'Oron',
  age: 27
};

const { name } = user;
console.log(name); // Oron
```

Pretty simple, right?!

Now, what if the object has a nested object and we want to extract a specific value from it.

![We need to go deeper MEME](/images/deeper.jpg)

Here's how:

```
const user = {
  id: 17,
  name: 'Oron',
  age: 27,
  residence: {
    previous: 'Rehovot',
    current: 'Tel Aviv-Yafo'
  }
};

const { residence: { current }} = user;
console.log(current); // Tel Aviv-Yafo
```

We can also rename it during destructuring:

```
const { residence: { current: city }} = user;
console.log(city); // Tel Aviv-Yafo
```

### Pro Tip

In some cases, the nested object might be missing, and we would end up with `TypeError`

```
const user = {
  id: 42,
  name: 'Daniel',
  age: 30,
};

const { residence: { current }} = user;
console.log(current); // TypeError: Cannot destructure property `current` of 'undefined' or 'null'
```

To prevent it, we can set a default value for the nested object

```
const { residence: { current } = {}} = user;
console.log(current); // undefined
```

