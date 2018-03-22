---
title: "git commit count"
date: 2018-03-22T17:37:11+02:00
draft: false
description: Count the number of commits between branches
tags: [git, commit, git-tricks, version-control]
keywords: [git, commit, git tricks, version control]
---
I have a tendency of creating many small commits when working on a new feature. 

While this may have some advantages, like ease of review, clear context and quick fallbacks, I find myself in need of
squashing these commits before the actual merge.

In order to use git's interactive rebase to rearrange my commits[1], I need to find out the number of relevant commits.    

Sure, I can  use [tig](https://jonas.github.io/tig/) or `git log --pretty=oneline` and simply count them, _but where's the fun in that?_

![Count commits](https://media.giphy.com/media/BmmfETghGOPrW/giphy.gif)

**_Today I learned_** how to count commits between different branches AWA within a branch.

\# of commits between master and the current branch:
```
$ git rev-list --count master..HEAD
```

* You can replace the `master` and `HEAD` parameters with any branch name or commit SHA

* The command uses `rev-list` flag which lists commit objects in reverse chronological order, then
counts them from the starting index to the final one.

[1] `$ git rebase -i HEAD~<number-of-commits>`
