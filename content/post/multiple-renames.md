---
title: "Mastering Renames"
date: 2018-05-27T23:27:17+03:00
draft: false
description: Rename multiple files from the terminal
tags: [cli, rename, terminal-tricks, macos, command, open-source]
keyword: [cli, rename, terminal tricks, macos, command, open source]
---
I was recently working on a ReactJS component which I called "Input". Not
anything fancy, an input field with two inner icons and a tailor-made CSS design.

I was ready to merge it when our designer brought to my notice that the proper
term was actually "Filter".    
At that point, making the change included renaming multiple `.jsx` files, as well as `.scss` and `.js`.

<img style="min-width:100%;" src="https://media1.tenor.com/images/3a4b04003a65f5db319b8130e62324d8/tenor.gif?itemid=10724708" alt="rename gif Ant-Man">

My first thought was to write a simple bash `for` loop with a `mv` command in its body. But it
seemed unlikely that a single command for the task doesn't exist and TBH, I was kinda lazy.

In a perfect timing I came across a handy [devhints.io](https://devhints.io/) tweet [Erik](https://twitter.com/erikzaadi) shared:

<blockquote class="twitter-tweet" data-cards="hidden" data-lang="en"><p lang="en" dir="ltr">CLI: change extensions easily using `rename`:<br>$ rename -s .jpg .jpeg *<br>⚡<a href="https://t.co/La6P7SPhOK">https://t.co/La6P7SPhOK</a> <a href="https://t.co/wEmCBYdSCZ">pic.twitter.com/wEmCBYdSCZ</a></p>&mdash; Devhints.io (@devhints) <a href="https://twitter.com/devhints/status/977455979372646400?ref_src=twsrc%5Etfw">March 24, 2018</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

While the tweet mentions its' ability to change extensions, `rename` can do much more, and it's [open
source](https://github.com/ap/rename) of course.

#### Installation

```shell
$ brew install rename
```

#### Usage
To solve my task with style all I needed was to type:
```shell
$ rename s/filter/input/gi *
```

I basically used a global (`g`), case insensitive(`i`) regex on all the files in my current dir.

<img style="min-width:70%;" alt="coolest name ever gif" src="https://media1.tenor.com/images/516f5941610e3bc2cfe71ddc20b97014/tenor.gif?itemid=11247562">

There are many alternatives for this type of change with rename, and various use cases for this awesome command.

`rename` supports options like text substitute (`-s`), `--camelcase`, `--trim`, remove extension (`-x`), append (`-a`) and more.

#### Pro Tip
Always use the `-n` flag which performs a _dry-run_, meaning it will only print a preview of the
outcome:
```shell
'BPFilter.jsx' would be renamed to 'BPinput.jsx'
'BPFilter.test.jsx' would be renamed to 'BPinput.test.jsx'
'bp_filter.scss' would be renamed to 'bp_input.scss'
```

For more info checkout the [rename website](http://plasmasturm.org/code/rename/)
