---
title: "git + hub = github"
date: 2018-01-30T21:33:12+02:00
draft: false
description: CLI tool for working with GitHub
tags: ["git", "github", "cli", "terminal-tricks", "open-source", "version-control", "hub", "pull-request"]
keywords: [git, GitHub, cli, terminal tricks, open source, version control, hub, pull request]
---
Opening a new pull request from GitHub's UI?
Copy-pasting the SSH/HTTPS url for cloning a repo?

_Ain't nobody got time for that!_

![Ain't nobody got time for that!](https://media.giphy.com/media/10PcMWwtZSYk2k/giphy.gif)

[hub](https://github.com/github/hub) is a command-line wrapper for `git` that makes you better at GitHub.

#### Usage
I've been using it for a while now and this is the gist:

* Create a new PR from your current branch:

```shell
$ hub pull-request -o
```
Will open your default editor to insert the header and description, then lunch a new browser tab to view it.
You can even add reviewers `[-r <REVIEWERS>]`

* Clone a GitHub repo:

```shell
$ hub clone github/hub
```
Expands to git@github.com:github/hub.git
Just replace 'github' with the repo's organization or user and 'hub' with its name.

#### Protip
As the docs suggest, hub is best aliased as git.
So feel free to add it to your .bashrc/.zshrc: `alias git=hub`

#### Installation
Follow the instruction and other examples [here](https://hub.github.com/)

The manual can be found [here](https://hub.github.com/hub.1.html)
