---
title: "Merge Python Dicts"
date: 2018-11-17T17:48:23+02:00
draft: false
images: [/images/python-wordcloud.jpg]
tags: [python, dict, dictionary, merge, combine, hash, map, hash-table, development]
keywords: [Python, Dict, Dictionary, Merge, Combine, Hash, Map, Hash Table, Development]
description: Merge dictionaries in Python >=3.5
---
Merging maps/hash tables is a pretty common operation in programming.

Though `Python` is my fallback language, only today I learned the new way all cool kids use to
combine dictionaries in Python 3.5 or higher.

Say we have two dicts:

```Python
>>> a = {'x': 1, 'y': 2}
>>> b = {'y': 3, 'z': 4}
```

What we want to end up with is a new dict `d` with merged values. In case the dicts have the same
key, the value of dict `b` will override `a`.

```Python
>>> d
{'x': 1, 'y': 3, 'z': 4}
```

The new way, using [PEP 448](https://www.python.org/dev/peps/pep-0448/) dictionary unpacking:

```Python
>>> c = {**a, **b}
>>> c
{'x': 1, 'y': 3, 'z': 4}
```

We can also add more key,value pairs:

```Python
>>> d = {**a, 'stan': 'lee', **b}
>>> d
{'x': 1, 'y': 3, 'Stan': 'Lee', 'z': 4}
```

![Stan Lee RIP](/images/stanlee-rip.jpg)

### Note

The Python 2 preferred way we all know and love is:

```Python
def merge_two_dicts(a, b):
    c = a.copy()
    c.update(b)
    return c

d = merge_two_dicts(a, b)
```
