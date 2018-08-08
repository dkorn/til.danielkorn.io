---
title: "Amend to that"
date: 2018-08-08T23:28:25+03:00
draft: false
description: Modify the last commit without changing its commit message 
tags: [git, commit, git-tricks, version-control, amend, no-edit]
keywords: [git, commit, git tricks, version control, amend, no edit]
---
Changing the last commit is a pretty common use case in Git.

Whether you forgot to add a file or simply want to revise the commit message, you will probably use
the `--amend` flag:

```bash
$ git commit --amend
```

It adds the staged changes to the previous commit and prompts your default editor to update the commit
message.

If you only wanna modify the commit message use the `-m` option:

```bash
$ git commit --amend -m "Boosted Commit Message"
```

But in many cases, we want to change the last commit _without editing the commit message_. 

**Today I Learned** how to do exactly that, just add the `--no-edit` flag:

```bash
$ git commit --amend --no-edit
```

No popup editor and two seconds saved.

![git commit amend](https://media.giphy.com/media/88iHW1fhm8Q9W3SRom/giphy.gif)

#### Note

The truth is, amending a commit actually replaces it entirely, resulting in a new commit with its own ref. 

Think twice before you do that when working on a commit shared with others, as it may cause merge conflicts. 
