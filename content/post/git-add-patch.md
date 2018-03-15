---
title: "git patch mode"
date: 2018-03-14T17:44:42+02:00
draft: false
description: Stage only parts of a changed file
tags: [git, add, patch, version-control, git-tricks]
keywords: [git, add, patch, version control, git tricks]
---
Once in a few pull-requests, I find myself splitting and redistributing my commits. I always try
to divide commits according to logical and related blocks of code, which can be easily reviewed.

This modular separation sometimes results in the need of staging only **_parts_** of a changed file, instead of the entire file.

The way to do it properly[1] in git is using `git add -p` (usually with the specific file path).

From git [docs](https://git-scm.com/docs/git-add#git-add--p):

> This effectively runs add --interactive, but bypasses the initial command menu and directly jumps to the patch subcommand.

After hitting enter you'll see part of the diff with a list of available subcommands[2] to choose
from:

![git patch -p result](/images/git-add-p.png)

There 3 options I use but keep forgetting, so I thought _why not til 'em?!_:

* `y/n` - Stage or not stage changes

* `s` - Split the current diff into smaller chunks you can stage separately

    ![split](/images/split.png)

* `e` - Manually edit the current diff
This is useful when splitting doesn't solve your problem if you need smaller chunks for example

    ![Manual Edit](/images/manual-edit.png)

    Adding the entire diff is easy as quitting [your default editor](https://stackoverflow.blog/2017/05/23/stack-overflow-helping-one-million-developers-exit-vim/), not staging lines is the tricky part.    
    I know, it is written in the commented instructions but still gets me
confused:

  - not staging a deleted line: change `'-'` to `' '` (space)

  - not staging an added line, marked with `'+'`: delete the entire line (`dd`)

    <blockquote class="twitter-tweet" data-lang="he"><p lang="en" dir="ltr">I&#39;ve been using Vim for about 2 years now, mostly because I can&#39;t figure out how to exit it.</p>&mdash; I Am Devloper (@iamdevloper) <a href="https://twitter.com/iamdevloper/status/435555976687923200?ref_src=twsrc%5Etfw">17 בפברואר 2014</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


[1] If you're OK with using a GUI I'd recommend [GitHub Desktop](https://desktop.github.com/), but
IMHO knowing the CLI can come in handy.

[2] subcommands details
![subcommands](/images/subcommands.png)

