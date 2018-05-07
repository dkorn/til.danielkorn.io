---
title: "Node Debugging"
date: 2018-05-07T10:18:42+03:00
draft: false
description: Debugging Node.js with Chrome DevTools
tags: [debug, inspect, chrome, dev-tools, nodemon, node, npm, javascript, nodejs, development, open-source]
keywords: [debug, inspect, chrome, dev tools, nodemon, node, npm, Javascript, nodejs, development, open source]
---
We all use good-ole `console.log()` to debug our JS code (see my previous [TIL](https://danielkorn.io/post/console-log/)). Sometimes it's just not enough.    
In those debug-hell situations, I call a debugger for the rescue.

![Debug Meme](/images/debug-meme.jpg)

Now before you say something like _"I have a great debugger in my webstorm"_, let me just
say it's perfectly fine.    
But for those complicated remote scenarios or when you're not
debugging using your working env, the following can become useful.

Coming from Python I always had [pdb](https://docs.python.org/3.4/library/pdb.html) to watch my
back.    
Well, that didn't work out for me with Nodejs built-in [debugger](https://nodejs.org/api/debugger.html). Call me lazy, but typing `repl` to play with my code then stepping back out, while most times killing the service, isn't my cup of tea.

![Debugging XKCD](/images/debugging-xkcd.png)

I was excited to stumble upon the great [node-inspector](https://www.npmjs.com/package/node-inspector),
which allowed me to debug in my browser.

**_Today I learned_** that as of version 6.3, Node.js comes with a built-in DevTools-based debugger which deprecates node-inspector!

The next few lines will give you the HOW-TO gist.

#### Usage

1. Run you Node service with the `--inspect` flag. Don't forget to use [nodemon](https://danielkorn.io/post/nodemon/)

    ```shell
    $ nodemon --inspect awesome-service.js
    ```

2. Open `chrome://inspect` in chrome. You'll see something like this:

    ![Chrome Inspect DevTools](/images/chrome_inspect.png)

3. Click the _Open dedicated DevTools for Node_ link

    ![Open Dedicated Link](/images/open_dedicated.png)

    A pop window will open, that's your debugger connected to Node right there.
    And it includes all the Chrome DevTools features we all love

    ![DevTools Debugger](/images/devtools_debugger.png)

Go ahead and add breakpoints, use blackboxing, live edit your source code, evaluate vars and
expressions in scope, use the console and take advantage of many more advanced options.

#### Pro Tip

Dark mode, all the cool kids are doing it.

Open DevTools -> Settings -> Prefernces, Appearance -> choose `Dark`

![DevTools Dark Theme](/images/devtools_dark_theme.png)


