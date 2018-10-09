---
title: "Keep in Trim"
date: 2018-10-09T20:42:35+03:00
draft: false
description: Mongoose trick for auto trimming strings
tags: [mongodb, mongoose, mongoose-tricks, db, model, schema, strings, JS, JavaScript]
keywords: [mongodb, mongoose, mongoose tricks, DB, model, schema, strings, JS, JavaScript]
---
Reviewing a candidate take-home coding assignment solution is usually not the most thrilling task.    
But when you get to learn a new trick, it gets much more interesting.

**__Today I learned__** about the `trim` flag for mongoose `String` schema type.

Say you define a new schema with a field of type `String`.    
Adding the `trim: true` option will always call JavaScript [.trim()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim) method on the string value when set.

I found it especially useful for 'email' fields.

#### Example

```JavaScript
const userSchema = new Schema({ email: { type: String, trim: true }})
const userModel = db.model('User', userSchema)

const email = '   til@danielkorn.io   '
console.log(email.length) // 23

const user = new userModel({ email: email })
console.log(user.email.length) // 17
```

Happy Trimming!
![Trimming gif](https://media.giphy.com/media/kh8EIea2n6ysM/giphy.gif)
