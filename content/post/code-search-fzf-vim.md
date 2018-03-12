---
title: "Search Code Like a Boss"
date: 2018-03-12T10:57:09+02:00
draft: false
description: "Vim code search using fzf and The Sliver Searcher"
tags: [fzf, vim, search, the-silver-searcher, search, Ag, vim-tricks]
keywords: [fzf, vim, search, the silver searcher, search, Ag, vim tricks]
---

When it comes to finding files and definitions, Vim has a fair share of plugins. I've tried [Command-T](https://github.com/wincent/command-t), [Ctrl-P](https://github.com/ctrlpvim/ctrlp.vim), and others before I moved to [fzf.vim](https://github.com/junegunn/fzf.vim).

`fzf.vim` is a Vim wrapper around some functionalities of the awesome [fzf](https://github.com/junegunn/fzf) command-line fuzzy finder.
`Files` and `Commits` are great commands fzf.vim allows, but I was looking for a way to easily search code in the current project.

**_Today I learned_** how to use the `Ag` command to search for the word under the cursor with optional args.
[Ag](https://github.com/ggreer/the_silver_searcher), or by its official name The Silver Searcher, is a code searching tool similar to ack, with a focus on speed.

#### Setup
After you install [Ag](https://github.com/ggreer/the_silver_searcher#installing), [fzf and
fzf.vim](https://github.com/junegunn/fzf.vim#installation), add the following key mapping[1] to your `.vimrc` file:

`nnoremap <Leader>a :Ag <C-R><C-W><CR>:cw<CR>`

Then just source your `.vimrc` file and you're done.

#### Usage
When in normal mode, place your cursor on the code you want to search and insert `<Leader>a`

A new pane will popup at the bottom of the Vim window with the search hits.

At this point, you can add more args, choose a result and open it in or close the pane.

![Ag Search gif](https://media.giphy.com/media/LUSTKCuzjR3AXfhvqB/giphy.gif)

[1] You can replace the `<Leader>a` with any other key you're more comfortable with.
