---
title: "Markdown All The Things"
date: 2018-01-29T21:13:55+02:00
draft: false
description: Markdown preview with live update
tags: ["markdown", "preview", "npm", "readme", "live-update", "open-source", "terminal-tricks", "node"]
---

By now I know most of the basic markdown syntax by heart.

Still, in most cases, I wanna take a look at the preview before pushing a GitHub `README.md`.
Especially if a cool ASCII art is included ;)

**_Today I Learned_** about [markdown-live](https://github.com/mobily/markdown-live), a useful node
package that fires up a new browser tab with the preview of your markdown file.

To make it even more awesome, it watches for changes in the file and updates the preview on save!

#### Usage
* watch markdown files in the _current directory_
```shell
$ mdlive
```

* watch a specific file
```shell
$ mdlive -f <file-name>
```

![markdown all the things](/images/markdown.jpeg)

#### Installation
```shell
$ npm install -g markdown-live
```


#### Demo
![](https://raw.githubusercontent.com/mobily/markdown-live/master/screencasts/gif1.gif)
