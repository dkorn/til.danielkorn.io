---
title: "Mongo String Queries"
date: 2018-07-18T23:23:52+03:00
draft: false 
description: Using regex to query strings in MongoDB
tags: [mongodb, mongo-tricks, regex, regular-expressions, db, strings, queries, case-sensitive]
keywords: [MongoDB, Mongo Tricks, regex, Regular Expressions, DB, Strings, Queries, Case Sensitive]
---
Some time ago I learned a useful MongoDB trick while pair programming.

If you tend to query using strings you may already know that MongoDB is by default case-sensitive.     

Querying: 
```
db.users.find({name: 'rafael nadal'})
``` 

is different from:
```
db.users.find({name: 'Rafael Nadal'})
```

Obviously, the best practice is to make sure your data is in a known case, but that might not always be
under your control.

#### Solution

Fortunately, it is possible to use `regex` in Mongo queries!

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/regular_expressions.png" alt="regex to da rescue">
  Regular Expressions by <a href="https://xkcd.com/208/">xkcd</a>
</p>

So in this case we can simply query:
```
db.users.find({name: /rafael nadal/i})
```

`i` is for ignoring case sensitivity.

![Rafael Nadal celebration](https://media.giphy.com/media/l3q2T74mddn74nRhC/giphy.gif)

There are other use cases for `regex`, like querying partial strings, though keep in mind
these queries are relatively slow.

