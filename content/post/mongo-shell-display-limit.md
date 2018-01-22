---
title: "Mongo Shell GIMME MORE"
date: 2018-01-22T16:32:22+02:00
draft: false
description: Changing the mongo shell batch size 
---
When retrieving documents in the mongo shell using the `find()` method, without assigning to a var, it will print only the first 20 documents that match the query. 

After which you'll get the infamous prompt:

```js
Type "it" for more
```

to iterate 20 more documents.


It can be extremely useful to increase the default number of displayed documents. 

To achieve that, all you need to do is to set `DBQuery.shellBatchSize` attribute:

```js
DBQuery.shellBatchSize = 100;
```

and voilà, you now have 100 documents returned.

![PLEASE SIR](/images/please-sir.jpg)

