---
title: "Shutdown Mac from the Terminal"
date: 2019-10-26T19:47:06+03:00
draft: false
description: How to shutdown, restart and put your Mac to sleep from the terminal
images: [/images/Mac-Os-X-Logo.png]
tags: [terminal, terminal-tricks, macos, macosx, cli, command-line, shutdown, restart, sleep,
reboot, halt]
keywords: [Terminal, Terminal Tricks, Mac OS X, CLI, Command Line, shutdown, restart, sleep,
reboot, halt]
---
I spend most of the time on my Mac working from the terminal.
And while there are several other ways to shutdown, restart or put the computer to sleep, I always
choose to do so using the command line. 

This is also useful for remote machine administration if you're using SSH or [mosh](https://danielkorn.io/post/mosh-mobile-shell/).

I know the topic seems pretty basic, and it is, but I was surprised to find out many colleagues of
mine don't use this method and thought it may be helpful for others.

### Usage

To perform all three operations you can use the [`shutdown`](https://ss64.com/osx/shutdown.html) command, which _"Close down the system at a given time"_.

*Shutdown*
```
$ sudo shutdown -h now
```

*Restart*
```
$ sudo shutdown -r now
```

*Sleep*
```
$ sudo shutdown -s now
```

- The command has to be run as root, so unless you're logged in you'll need to prefix it with `sudo`

- In case you want to delay the operation in X minutes, just specify the number after the `-h` flag
```bash
$ sudo shutdown -h +60
```
Will shutdown the Mac in 60 minutes. 

### Pro Tip

I use these aliases in my `.zshrc`

```
alias restart="sudo shutdown -r now"
alias shutdown="sudo shutdown -h now"
alias sleep="sudo shutdown -s now"
```

![Mac OS X Logo](/images/shutdown.png)
