---
title: "Notify Me"
date: 2018-10-14T21:39:45+03:00
draft: false
description: Get notified when a long-running process is finished
tags: [terminal-tricks, notifications, alerts, monitor, process, open-source, shell, developer-tricks]
keywords: [terminal tricks, notifications, alerts, monitor, process, open source, shell, developer tricks]
---
How many times did you sit and wait for a docker image download?    
Are you tired of looking at the terminal while `npm` installs all packages as I am?

**_Today I learned_** about [noti](https://github.com/variadico/noti), an open source `golang` based
terminal tool that monitors a process and triggers a notification when it's done.

#### Usage

Once installed, all you need to do is add `noti` in the beginning or end of your command

```
$ noti npm install
```

![noti banner notification](/images/noti.png)


#### Pro Tip

Forgot to use noti? leverage the `--pwatch` option with the process ID

```
$ noti --pwatch $(pgrep docker-compose)
```

It will trigger a notification when the pid disappears.

#### Installation

On macOS:

```shell
$ brew install noti
```

On any other:
```shell
$ go get -u github.com/variadico/noti/cmd/noti
```
