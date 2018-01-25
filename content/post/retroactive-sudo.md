---
title: "Retroactive sudo"
date: 2018-01-19T17:23:15+02:00
draft: false
description: forgot to `sudo` before editing a file with Vim? No worries
tags: ["sudo", "vim", "permissions", "command", "vimtricks"]
---

It happened to me countless times - forgetting to `sudo` before I start editing a file I don't have
permission on using Vim.

I used to save the edited file to a temporary location when the permission error prompt, and copy it back again.

**_Today I Learned_** this awesome command:

```
:w !sudo tee %
```

#### Command Explained
* `:w !cmd` - write the current buffer piped through command

* `%`       - the filename associated with the buffer

* `tee`     - used to store and view (both at the same time) the output of any other command

`:w !sudo tee %` will pipe the contents of the buffer through `sudo tee FILENAME`.

![HACKERMAN](/images/sudo.png)
