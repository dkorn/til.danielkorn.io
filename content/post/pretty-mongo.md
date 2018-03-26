---
title: "Pretty Please"
date: 2018-03-25T16:34:17+03:00
draft: false
description: Prettify your MongoDB Shell results
tags: [mongodb, mongo-tricks, mongo-shell, mongo-hacker, db, pretty]
keywords: [MongoDB, Mongo Tricks, MongoDB Shell, mongo-hacker, DB, pretty]
---
If you're using MongoDB you're most likely working daily with its [shell](https://docs.mongodb.com/manual/mongo/#the-mongo-shell).

Probably the first thing I learned about this interactive JavaScript interface was adding the [`pretty()`](https://docs.mongodb.com/manual/reference/method/cursor.pretty/#cursor.pretty) method to all queries, to make it easier to read the results.

After few manual types, I decided to use `pretty()` by default.

To do so for a specific session:
```js
(mongod-3.6.0) test> DBQuery.prototype._prettyShell = true
```

To enable it globally just add it to your `$HOME/.mongorc.js`:

```bash
$ echo DBQuery.prototype._prettyShell = true >> ~/.mongorc.js
```

![Pretty](/images/pretty.jpg)

#### PRO TIP
For local development, I use Tyler Brock's [mongo-hacker](https://github.com/TylerBrock/mongo-hacker).

I recommend trying it even if you're only interested in UX enhancement (there are many more great
features...).

```bash
$ npm install -g mongo-hacker
```

![So Pretty](https://media1.tenor.com/images/ecc5aec621cd21ade1d514cdbc1e9812/tenor.gif?itemid=4093619)

If you're interested in changing the mongo shell batch size checkout my previous [til](https://danielkorn.io/post/mongo-shell-display-limit/).
