---
title: "howdoi"
date: 2018-09-05T23:13:21+03:00
draft: false
description: Instant answers to coding question via the CLI
tags: [open-source, shell, terminal-tricks, command-line, cli, dev-tricks]
keywords: [open source, shell, terminal tricks, command line, CLI, developer tricks]
---
How many times have you left the terminal to search the web for a coding solution?

Whether it is the Python dict comprehension, a CSS Flexbox property, `sed` command syntax or the
order of commits during `git squash`.

Today I learned about the AMAZING [howdoi](https://github.com/gleitz/howdoi) command line tool.

It quickly scrapes code from StackOverflow top answers and outputs the solution in your terminal.

#### Installation

```shell
$ pip install howdoi
```

#### Usage

```shell
$ howdoi untar a tar file
tar –xzf filename.tgz -C /target/directory
```

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/tar.png" alt="XKCD tar">
  TAR by <a href="https://xkcd.com/1168/">xkcd</a>
</p>

You can change the source url for answers, the underline search engine and even colorize the output.
