---
title: "Tmux fpp"
date: 2018-11-16T16:27:59+02:00
draft: false
description: Quickly open files from commands output
tags: [fpp, tmux, cli, terminal-tricks, command-line, open-source]
keywords: [fpp, tmux, CLI, Terminal Tricks, Command Line, Open Source]
images: [/images/tmux-logo.png]
---
I don't always install a new [tmux](https://github.com/tmux/tmux/wiki) plugin, but when I do I write a TIL about it :)

Today, the FP guru and Scala master [Daniel Sebban](https://twitter.com/dsebban) showed me [tmux-fpp](https://github.com/tmux-plugins/tmux-fpp).    
It is a wrapper around [Facebook PathPicker](https://facebook.github.io/PathPicker/), that allows you to
quickly open files in your default editor, from different commands output.

### Installation

1. Install Facebook PathPicker using [Homebrew](https://formulae.brew.sh/formula/fpp) on macOS
 
    ```shell
    $ brew install fpp 
    ```

2. Using [TPM](https://github.com/tmux-plugins/tpm), add 'tmux-plugins/tmux-fpp' to the list of plugins in
   your `.tmux.conf` file, and enter `prefix + I` to install it.

### Usage

I found tmux-fpp mostly useful for `git` commands output and `grep` results.    

After executing a certain command, hit `prefix f` to open a cool UI to select the files you're
interested in.     
Press `f` while the cursor is on a specific path to mark the desired files, then `Enter` and the
files will open in your `$EDITOR` of choice.

<video width="100%" height="320" controls>
  <source src="/images/tmux-fpp.mov" type="video/mp4">
</video>
