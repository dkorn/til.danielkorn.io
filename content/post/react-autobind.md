---
title: .bind(this) no more!
date: 2018-06-03T18:47:57+03:00
draft: false 
description: Autobinding Event Handlers in React
tags: [reactjs, react, component, js, bind, this, javascript, nodejs, npm]
keyword: [ReactJS, React, Component, JS, bind, this, JavaScript, Nodejs, npm]
---
If you're working on a React/React Native project you've probably had to deal with binding event
handlers.     
It isn't a React specific issue, but a part of the way functions work in JavaScript.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">To bind or not to bind? It’s all about those parens. <a href="https://t.co/b7pi4kxyfi">pic.twitter.com/b7pi4kxyfi</a></p>&mdash; Dan Abramov (@dan_abramov) <a href="https://twitter.com/dan_abramov/status/790612782471319553?ref_src=twsrc%5Etfw">October 24, 2016</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

Manually binding each component method may sound considerable. 
This is the "old school" way - bind in `constructor()`:

```
this.handleClick = this.handleClick.bind(this);
```

But believe me when I tell you, repeating it for 5+ methods is both annoying and quite ugly:

```
this.addComment = this.addComment.bind(this)
this.removeComment = this.removeComment.bind(this)
this.editComment = this.editComment.bind(this)
this.fetchComments = this.fetchComments.bind(this)
this.clapComment = this.clapComment.bind(this)
this.bookmarkComment = this.bookmarkComment.bind(this)
```

![Nasty gif](https://media.giphy.com/media/1bYaHhGtueIqQ/giphy.gif)

While I'm a big fan of arrow function expressions and the [public class field feature](https://babeljs.io/docs/plugins/transform-class-properties/), which uses the first to solve the problem ("Lexical Scoping"), it is still experimental and not yet part of ECMAScript standard (stage 3).

#### Solution - Autobinding Packages

There are 3 packages I came across:

1. [Autobind Decorator](https://www.npmjs.com/package/autobind-decorator) - Coming from Python,
   the decorators pattern of adding `@autobind` before methods seemed almost natural.     
   But I get why developers prefer not to add a line above each individual method inside every React component.

2. [Class Autobind](https://www.npmjs.com/package/class-autobind) - The package we chose in [BigPanda](https://www.bigpanda.io/). It uses a function inside your constructor that automatically binds the Component's methods to the instance itself:
   ```
   class MyComponent extends React.Component {
    constructor(props) {
      super(props);
      autobind(this);
  }
   ```
   In case you plan to subclass the component, specify the prototype as the second parameter.


3. [React Autobind](https://www.npmjs.com/package/react-autobind) - Useful when you want to select
   specific methods to bind.

Let me know if you have different solutions.
