---
title: "Vim Search & Replace"
date: 2018-08-20T15:43:02+03:00
draft: false
description: Multiple files search and replace in Vim
tags: ["vim", "search", "replace", "find", "vim-tricks"]
---
Most IDEs today includes a built-in way of searching and replacing a pattern across multiple files. *Vim* is no different.

Like many operations in Vim, there are 2 approaches you can take:

1. The "pure"/"native" way

2. Using a plugin

Today I needed to rename a `ReactJS` component from "NewRoleModal" to "RoleModal". Let's use this
example.

#### The Native Approach

Utilize day-to-day CLI commands for the job, in two steps:

1. Search all file names that include the term "NewRoleModal" in the relevant path, and set the
   result into the argslist.

    ```sh
    :args `grep -rl 'NewRoleModal' app/react/modules`
    ```

  * If you want to check the content of the argslist just type `:args`.

  * Feel free to use your favorite search command here instead of `grep` (e.g. `ack`, `git grep`
    etc.)

2. Perform the replace action on all the search results and save.

    ```sh
    :argdo %s/NewRoleModal/RoleModal/g | update
    ```

    * `argdo` iterates over all files and executes the substitution command. 

    * `update` saves the input from the piped result, meaning the changed files.


#### The "Easy" approach

[Erik](https://github.com/erikzaadi/) recommended me the straightforward [vim-easygrep](https://github.com/dkprice/vim-easygrep) plugin.

After installation[1] just use the `Replace` command:

```
:Replace NewRoleModal RoleModal
```

A useful keymapping I found is `<Leader>vr` - "perform a global search on the word under the cursor and prompt for a pattern with which to replace it."


![Search and Replace MEME](/images/searchnreplace.jpg)

[1] Add `dkprice/vim-easygrep` to `.vimrc` with your preferred plugin manager.
