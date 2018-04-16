---
title: "No Demon!"
date: 2018-04-16T00:19:38+03:00
draft: false
description: Use nodemon for node.js app development
tags: [nodemon, node, npm, nodejs, development, watch, restart, open-source]
keywords: [nodemon, node, npm, nodejs, development, watch, restart, open source]
---
_Developing a node.js based service?_    
_Fed up with manually restarting your app every time you make a change?_

If you've answered **_yes_** to both questions give [nodemon](https://nodemon.io/) a try.

`nodemon` will monitor the files in the directory, and in case of a change - it will automatically restart your node application.

![No Demon](https://tenor.com/view/friends-phobe-no-demon-scared-gif-3394822.gif)

#### Installation

```shell
$ npm install -g nodemon
```
#### Usage

Since nodemon is a replacement wrapper for node that watches for changes, just replace `node` with `nodemon` when you run your script:

```shell
$ nodemon my_service.js
```

In case you need a manual restart of your app type `rs` followed by a `return`, instead of stopping
and restarting nodemon.

I recommend adding a `dev` script under npm scripts in `package.json` file:

```
{
  "scripts": {
    "start": "node my_app.js",
    "dev": "nodemon my_app.js"
  }
}
```

There are other features I found useful:

* Using config files or `nodemonConfig` in the package.json file
* Specifying extension watch list: `nodemon -e js,json`
* Monitoring multiple directories: `--watch` flag per directory watched

![nodemon logo](/images/nodemon.png)

_**Note**: I plan to cover debugging with nodemon in a separate post._
