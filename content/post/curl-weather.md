---
title: "Sweater Weather"
date: 2018-01-23T16:20:03+02:00
draft: false
description: Check the weather from your terminal using `curl`
tags: ["curl", "weather", "forecast", "terminal", "open-source", "shell", "terminal-tricks", "command"]
---

I was looking for a way to get the forecast from the terminal, _because why not?_ :) 

Sure, I can browse to AccuWeather/The Weather Channel and after few clicks get what I wanted, but where's the
fun in that?

I came across this great open source project: [wttr.in](https://github.com/chubin/wttr.in/).    
It's basically a web frontend for [wego](https://github.com/schachmat/wego), a terminal weather app with awesome ASCII art, that brings you all da sh\*t with nothing but `curl`!

#### Usage

```shell
$ curl wttr.in/tel-aviv
```

![Tel-Aviv Weather](/images/wttr-tel-aviv.png)

#### Advanced Features

* Dropping the location name will return the report for your current location, based on IP address, but it's **not** so accurate
* Use 3-letters airport codes to get their weather info:
```
$ curl wttr.in/jfk
```
* To query a name of some geographical location/site place `~` before its name:
```
$ curl wttr.in/~santiago-bernabeu-stadium
```
* It is also possible to specify a domain name or IP address with `@` prefix:
```
$ curl wttr.in/@bigpnada.io
```
* Rule of thumb - USCS units for USA originated qeuries, metric system for the rest
* Help:
```
$ curl wttr.in/:help
```

#### Bonus Eye Candy
Do yourself a favor and type:
```shell
$ curl wttr.in/Moon
```

![Moon](/images/wttr-moon.png)

![Olaf WoW](https://media.giphy.com/media/FZiXDhzZJmHzq/giphy.gif)
