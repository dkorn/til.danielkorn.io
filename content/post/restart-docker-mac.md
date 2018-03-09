---
title: "Restart Docker for Mac Command"
date: 2018-03-09T22:23:34+02:00
draft: false
description: Restart Docker for Mac from the terminal
tags: [docker, containers, terminal-tricks, macos, service, osascript]
keywords: [docker, containers, terminal tricks, Mac OS X, service, osascript]
---

[Docker for Mac](https://docs.docker.com/docker-for-mac/) is the best way to get started with Docker on a Mac.

Though some versions have a restart button in the dropdown menu, I was looking for a
command to restart the service from the terminal.

![Docker for Mac dropdown menu](/images/docker-menu.png)

**_Today I learned_** how to do it with a combination of two simple commands.

As Docker for Mac is a Mac OS GUI app we can use `osascript`[1] command to gracefully quit it:
```
$ osascript -e 'quit app "Docker"'
```

To start the app:
```
$ open -a Docker
```

#### Pro Tip 

Add it as an alias in your .zshrc / .bashrc:    
`alias docker_restart="osascript -e 'quit app \"Docker\"' && open -a Docker"`

![Say Docker one more time meme](/images/say-docker.jpeg)

[1] Read more about [osascript](http://osxdaily.com/2014/09/05/gracefully-quit-application-command-line/)
