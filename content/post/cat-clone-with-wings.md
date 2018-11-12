---
title: "cat clone with wings"
date: 2018-11-11T23:20:21+02:00
draft: false
description: cat with Syntax Highlighting and Git Integration
images: [/images/bat.png]
tags: [terminal-tricks, command-line, cli, open-source, posix, cat, bat]
keywords: [Terminal Tricks, Command Line, CLI, Open Source, POSIX, cat, bat]
---
As a terminal user, I'm pretty sure I use `cat` command daily.

**_Today I learned_** about [`bat`](https://github.com/sharkdp/bat), a `cat` clone with syntax highlighting and Git integration.

![bat logo](/images/bat.png)

## Usage

Just add `bat` before the file/s you want to print

![syntax highlighting example](/images/syntax-highlighting.png)

Git integration

![git integration example](/images/bat-git.png)

`bat` supports automatic paging, so if your file is too large for the screen it will automatically
pipe the output to `less`.

It can read from stdin and automatically determine the syntax, though you can always specify it
explicitly with the `-l` option.

## Installation

on macOS with [Homebrew](https://formulae.brew.sh/formula/bat)

```shell
$ brew install bat
```

## Pro Tips

1. You can choose your favorite theme, out of the available options (`bat --list-themes`), using
   `--theme=` flag.
   
    ![bat DarkNeon theme](/images/bat-darkneon.png)

    For more advanced configuration, search for the `--style` option and its possible values.

2. Add `-A / --show-all` flag to highlight non-printable characters
