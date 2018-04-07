---
title: "gtop Monitoring"
date: 2018-04-06T09:43:25+03:00
draft: false
description: System monitoring dashboard for terminal
tags: [system-monitoring, process-viewer, top, dashboard, terminal-tricks, command, open-source]
keywords: [system monitoring, process viewer, top, dashboard, terminal, command, open source]
---
If you're working with Linux/MacOS terminal you've probably used the `top` command to monitor processes and system resource usage.

While `top` and its improved [`htop`](https://github.com/hishamhm/htop) are great for process
management, IMHO they lack the convenient dashboard-like view.

_**Today I learned**_ about [gtop](https://github.com/aksakalli/gtop) fancy system monitoring dashboard for terminal.

![gtop Monitoring Screenshot](/images/gtop.png)


#### Installation

```shell
$ npm install gtop -g
```

#### Usage

Start the process with
```shell
$ gtop
```

Use the following keys to sort the process table:

* `p`: Process Id
* `c`: CPU usage
* `m`: Memory usage


![Top Gun](https://media.giphy.com/media/3EuAsjZDUJefK/giphy.gif)

#### Disclaimers

* `gtop` doesn't have a built-in kill process option, though there is a feature request for it.

* For the above reason and others, I'd still use `top` or `htop` for **server** monitoring, if you don't have any advanced monitoring solution.
