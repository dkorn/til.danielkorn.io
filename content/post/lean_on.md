---
title: "lean() on"
date: 2018-04-29T16:51:25+03:00
draft: false
description: Improve query performance with mongoose lean
tags: [mongo, mongodb, mongoose, query, optimization, performance, JS, nodejs]
keywords: [mongo, MongoDB, mongoose, query, optimization, performance, JS, nodejs]
---

After a few months of in production, one of our microservices had some performance issues.
I was given the task of optimizing its' DB queries.

![optimization](/images/optimization.png)

Though my experience with [mongoose](http://mongoosejs.com/) and MongoDB isn't vast, I was able to find
few quick wins. The first one was using mongoose's `lean()` option.

By default, mongoose converts plain javascript objects returned from MongoDB to [MongooseDocuments](http://mongoosejs.com/docs/api.html#document-js).    
These mongoose objects contain some mongoose magic, including the `save` method, getters/setters and more.

But with this extra functionality comes an overhead which affects the query's performance...

Adding the `lean()` option prevents the mongoose document creation and returns a plain javascript
object, thus resulting in better performance.

#### Usage Example

```js
InfinityStones.find({name: 'Soul Stone'}).exec()
```

Now with lean:

```js
InfinityStones.find({name: 'Soul Stone'}).lean().exec()
```

And that's it

![lean](https://media.giphy.com/media/26gR1iYzSqtzcta4E/giphy.gif)

In addition to `find()`, the following queries also supports `lean`: `findOne()`, `findById()`, `findOneAndUpdate()`, and `findByIdAndUpdate()`.

To conclude, the rule of thumb I found for using `lean` is this:    

_If your query is mostly focused on reading the data, with no need of mongoose functionality for advanced manipulations - add_ `lean`

[![Lean On youtube link](https://img.youtube.com/vi/YqeW9_5kURI/0.jpg)](https://www.youtube.com/watch?v=YqeW9_5kURI)
