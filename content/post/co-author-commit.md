---
title: "Share The Credit, Accept The Blame"
date: 2018-02-06T17:49:30+02:00
draft: false
description: Creating co-authored commits
tags: ["git", "commit", "pairing", "pair-programming", "co-author", "github"]
---
Not something I learned today, but definitely useful enough to spare future searches.

It is quite often that we pair-program a task in the [startup I work for](https://bigpanda.io/).    

![Pair Programming](https://imgur.com/xIS8if1.gif)

To avoid sensitivities, share the credit and the blame, I recommend to co-author commits.    
All you need to do is add the following on the bottom of the commit message:

```shell
Co-authored-by: name <name@example.com>
```

Add multiple co-authors by giving each one their own line.

#### Bonus
In case you don't remember your user name or email type:
```shell
$ git config --global user.name
dkorn

$ git config --global user.email
korndaniel1@gmail.com
```

> I frequently say that I never share blame, I never share credit, and I never share desserts!

> Beverly Sills
