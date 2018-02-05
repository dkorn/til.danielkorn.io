---
title: "Winning with console.logs"
date: 2018-02-05T19:03:22+02:00
draft: false
description: Useful trick for JavaScript debugging
tags: ["JS", "debug", "ES6", "log", "javascript", "debugging"]
---
Using `console.log()` for JS debugging? You're gonna love this <3

Say we have
```javascript
const a = 1, b = 2, c = 3
```

we can log them as an object
```javascript
 console.log({ a, b, c })
 ```

and ta-da
```javascript
{
  a: 1,
  b: 2,
  c: 3
}
```

![satisfying logs](https://media.giphy.com/media/rOWcwUZGcbSnK/giphy.gif)
