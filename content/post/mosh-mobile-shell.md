---
title: "Mosh Mobile Shell"
date: 2018-02-12T17:44:59+02:00
draft: false
description: Why I replaced SSH with Mosh
tags: ["mosh", "mobile-shell", "remote-terminal", "ssh", "terminal-tricks", "open-source"]
keywords: [mosh, mobile shell, remote terminal, ssh, terminal tricks, open source]
---
If you regularly use `ssh` to securely connect to remote servers - keep reading

Mosh is an open source remote terminal application that replaces `ssh`.    
It allows _almost_ everything `ssh` does, with these game-changing features:

* Keeps session even if the connection is lost or you put your laptop to sleep (!)

* Stays connected if your IP is changed

* Instant response when typing, regardless of network lag or slow connection

* Control-C just works

* No root rights needed

* Same credentials for remote login

#### Usage

Just replace `ssh` with `mosh`:
```shell
$ mosh danielkorn.io
```

With a different user
```shell
$ mosh dkorn@danielkorn.io
```

#### Installation 

And other details, can be found [here](https://mosh.org/)

![Mosh Mobile Shell](/images/mosh.png)
