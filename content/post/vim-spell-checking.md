---
title: "Spell Checking in Vim"
date: 2018-02-01T20:55:32+02:00
draft: false
description: Perform spellchecking in vim like a boss
tags: ["vim", "spell", "spell-checking"]
---
The feeling I get when someone points to a typo in my PR:

![embarrassed](https://media1.tenor.com/images/6dc20467975b4c21ee6ff89eed842191/tenor.gif)

To avoid this from happening I added spell checking to the
editor I use to write code, and practically everything else - Vim.

#### Getting Started

Add the following to your .vimrc:
```shell
set spell spelllang=en_us
```

#### Usage
All commands refer to the word under the cursor

* `z=` - see suggestions for misspelled word

* `zg` - add word to your personal "_good words_" in the spellfile

* `zG` - ignore the misspelled word for this session (not stored and lost when you exit Vim)

* `]s`/`[s` - jump to next/previous misspelled word.    
A good practice is to go over them before
  publishing your changes.

* `zw` - mark word as misspelled

The full docs are [here](http://vimdoc.sourceforge.net/htmldoc/spell.html)

#### Bonus
Add the following to your .vimrc to get word completion:
```shell
set complete+=kspell
```

Just press CTRL-N or CTRL-P in insert-mode while typing.
