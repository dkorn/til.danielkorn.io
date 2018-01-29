---
title: "Trailing Whitespace, No More!"
date: 2018-01-25T17:33:46+02:00
draft: false
description: Vim plugin that highlights and cleans all trailing whitespace
tags: ["vim", "vimrc", "vim-plugin", "trailing-whitespace", "open-source"]
---

Nobody likes trailing whitespace.
I usually notice them only when looking at my committed changes.

Stripping extra white space always seemed like something I shouldn't worry about.

**_Today I learned_** about a cool vim plugin called [vim-better-whitespace](https://github.com/ntpeters/vim-better-whitespace), by [ntpeters](https://github.com/ntpeters).

#### The Basics

After installation using your favorite plugin manager, try the following

* Toggle whitespace highlighting on/off:
```
:ToggleWhitespace
```
* Clean extra whitespace:
```
:StripWhitespace
```
* To enable stripping of extra whitespace on file save add this line[1] to your `.vimrc`:

```shell
autocmd BufEnter * if index(g:better_whitespace_filetypes_blacklist, &ft) < 0 | exec 'EnableStripWhitespaceOnSave' | endif
```

[1] There's an open issue regarding the use of blacklist file types when enabling whitespace stripping on
file save. The line I wrote above is the author's suggested fix.

![trailing whitespace is bad mkay](/images/trailing-whitespace.jpg)

Learn more and contribute at [GitHub](https://github.com/ntpeters/vim-better-whitespace)
 or [Vim.org](http://www.vim.org/scripts/script.php?script_id=4859).
