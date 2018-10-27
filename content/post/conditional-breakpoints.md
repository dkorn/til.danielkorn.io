---
title: "Conditional Breakpoints"
date: 2018-10-26T18:55:20+03:00
draft: false
description: Conditional breakpoints in Chrome DevTools
tags: [conditional-breakpoint, debug, inspect, chrome, DevTools, javascript, nodejs, development]
keywords: [Conditional Breakpoint, debug, inspect, chrome, DevTools, javascript, nodejs, development]
---
I wrote about JS debugging using Chrome Developer Tools [in the past](https://danielkorn.io/post/node-debugging/).

Today, while pairing with [Oleg](https://twitter.com/OlegMostepan), I learned about **Conditional Breakpoints**.

This type of breakpoints is useful in case you want to pause inside a code block, but only when a defined condition evaluates to true.

#### Usage

Setting a conditional line-of-code breakpoint is much like the "regular" breakpoint.     
Choose the desired file in the _Sources_ tab, then go the line where the code you're looking for.

Now comes the small difference:

1. Right-click the line of code number and select _Add conditional breakpoint_

2. Enter the condition in the displayed dialog

3. Press `Enter` to activate. You'll notice that a new icon appears, but it is orange instead of
   blue.

And that's it, you're all set for debugging, with an extra tool in your box.

![conditional breakpoint gif](https://media.giphy.com/media/d5NKbK4H6XC6bM7jvP/giphy.gif)
