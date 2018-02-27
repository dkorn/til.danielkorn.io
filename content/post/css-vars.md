---
title: "CSS Variables"
date: 2018-02-27T13:17:13+02:00
draft: false
description: CSS Custom Properties Basics
tags: [frontend, FE, CSS, vars, variables, JS, JavaScript, custom-properties]
keywords: [frontend, FE, CSS, vars, variables, JS, JavaScript, Custom Properties]
---
I've used variables in SASS and LESS before, but I always prefer the native approach.

**_Today I learned_** the basics of CSS Custom Properties, also known as Variables.

#### General

* Like other variables, CSS Custom Properties lives in the scope they were declared in

* Variables are inherited. Therefore, defining a var on the `:root` class will make it global
  (`<html>` tag).

* CSS Variables have access to the DOM, unlike SASS and LESS. This means you can leverage things like screen size to update your variables.

![CSS by Peter Griffin](https://media.giphy.com/media/13XW2MJE0XCoM0/giphy.gif)

#### Usage

* Declaration: the property should start with two dashes
```
.example {
      --example-color: #ffff66;
}
```

* Access: use the `var()` function, and pass in the name of the variable as the parameter
```
#title {
      color: var(--example-color);
}
```

* Access vars with JavaScript

```
const example = document.getElementsByClassName('example');
const exampleStyles = getComputedStyle(example);
exampleStyles.getPropertyValue('--example-color');
-> #ffff66

example.style.setProperty('--example-color', '#3399ff')
```

#### Browser compatibility

![browser compatibility table](/images/table.png)
_taken from [MDN web docs](https://developer.mozilla.org/en-US/docs/Web/CSS/--*)_
