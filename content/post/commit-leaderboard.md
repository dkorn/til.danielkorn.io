---
title: "Commit Leaderboard"
date: 2018-06-19T17:48:51+03:00
draft: false 
description: List project contributors by number of commits 
tags: [git, commit, count, shortlog, git-tricks, version-control]
keywords: [git, commit, count, shortlog, git tricks, version control]
---
Not sure If you'll find this post too useful, but if you're even a little competitive you might enjoy it.

Ranking the authors in a specific repo by commit from the terminal:

```bash
$ git shortlog -s -n
```

The output would look like that:
```bash
    44  erikzaadi
    40  dkorn
     5  Guy Perkal
     1  yarden mintz
```

#### Explanation

* `git shortlog` - Summarize 'git log' output
* `-n, --numbered` - Sort output according to the number of commits per author
* `-s, --summary` - Suppress commit descriptions, only provides commit count

To show each author's email add `-e, --email`

#### Pro Tip

If you want statistics for all branches, including not yet merged, add:    
`--all --no-merges`.
