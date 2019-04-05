---
title: "Timemachine for Visual Testing"
date: 2019-04-03T18:21:11+03:00
draft: false
description: Monkey patch the `Date` object and override system time 
images: [/images/DeLorean.jpg]
tags: [timemachine, javascript, date, time, visual-tests, monkey-patch]
keywords: [Time Machine, JavaScript, Date, Time, Visual Tests, Monkey Patching]
---
<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/time_machine_xkcd.png" alt="XKCD Time Machine">
  Time Machine by <a href="https://xkcd.com/716/">xkcd</a>
</p>

A few days ago I added visual testing to our ReactJS-based components library.

Pretty early in the process, I encountered a consistency problem that caused false positive errors.    
The reason was, several components are using the _current_ date/time, thus failing the tests.

My first thought was going with the "naive" approach - using a constant datetime along all relevant
components visual examples (stories in [Storybook](https://storybook.js.org/), for example). Aside from not being an elegant solution, it requires anyone who
writes a component in the future to keep in mind using const date and time. Not easily maintainable.

That's when I found [`timemachine`](https://github.com/schickling/timemachine).

It is aimed to *"test your time-dependent app by monkey patching the `Date` function and overriding your system
time"*

## Usage

To set a date:

```
timemachine.config({
  dateString: 'March 4, 2017 18:21:11'
});
```

If you're using Storybook, add it to your `.storybook/config.js`

Now with every new call to `Date`:

```
console.log(new Date()); // March 4, 2017 18:21:11
```

Reset:

```
timemachine.reset();
```

## Installation

```shell
$ npm install --save-dev timemachine
```

![DeLorean](/images/DeLorean.jpg)
