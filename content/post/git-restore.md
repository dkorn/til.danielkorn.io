---
title: "git restore"
date: 2018-04-10T11:32:58+03:00
draft: false
description: Restore folders and files with git
tags: [git, checkout, version-control, git-tricks, restore, revert, pick]
keywords: [git, checkout, version control, git tricks, restore, revert, pick]
---
With `git` it seems you can always learn new hacks.

Today, a colleague of mine asked me if I know a quick way to restore a deleted folder from a past commit.

![Version control xkcd strip](/images/vc-xkcd.jpg)

My first thought was the _naive_ solution:     
checkout a specific commit containing the directory, copy it to `/tmp`, return `HEAD` to your working branch and copy the folder to it.

_way too naive, I know..._

Then, another [colleague](https://twitter.com/Idan_Co?lang=en) suggested I'll take a look at [`git checkout`](https://git-scm.com/docs/git-checkout) command documentation, and it
delivered!

#### Solution

To restore a folder or a file from a specific commit:    
`git checkout <commit SHA> -- <file|foldername>`

Example:

```shell
$ git checkout 797d624 -- deleted_folder
```

![Salvage xkcd strip](/images/salvage-xkcd.png)

*Note*: This can be also used to pick a file from a change not yet merged (commit in a PR), for review and testing.
