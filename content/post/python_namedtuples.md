---
title: "Namedtuples"
date: 2018-04-21T16:34:34+03:00
draft: false
description: Using Python's namedtuple()
tags: [python, collections, namedtuple, python-modules]
keywords: [python, collections, namedtuple, python modules]
---

Out of the handy [collections](https://docs.python.org/2/library/collections.html#module-collections) module, I'm using `namedtuple` datatype the most.

Once instantiated, [namedtuples](https://docs.python.org/2/library/collections.html#collections.namedtuple) can be used like regular tuples:

```python
>>> from collections import namedtuple

>>> Dog = namedtuple('Dog', 'age breed color')
>>> rachel = Dog(2, 'Pomeranian', 'Brown')

>>> rachel[0]
2

>>> name, breed, color = rachel
>>> color
'Brown'
```

With the advantage of accessing the fields by attribute (name) lookup:

```Python
>>> rachel.breed
'Pomeranian'
```

And an awesome string `__repr__()` with a `name=value` style:

```Python
>>> rachel
Dog(age=2, breed='Pomeranian', color='Brown')
```

#### Main Use cases

I found namedtuple especially useful when:

* Grouping multiple values, in a shorter way than manually defining a class
* When a function returns several values (say more than 3) returning a namedtuple makes it easier to
  unpack them

![Pomeranian](/images/Pomeranian.png)

#### Tips & tricks 

* To view the fields names use `_fields` method

* Tuples are immutable, therefore you'll need to use the `_replace` method to change a value:

```Python
>>> rachel.color = 'Tan'
AttributeError: "can't set attribute"

>>> rachel._replace(color='Tan')
Dog(age=2, breed='Pomeranian', color='Tan')
```

* To convert a dictionary to a named tuple:

```Python
>>> pepsi = {'age': 12, 'breed': 'Belgian Shepherd', 'color': 'Black'}
>>> Dog(**dict)
Dog(age=12, breed='Belgian Shepherd', color='Black')
```
