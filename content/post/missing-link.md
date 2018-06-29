---
title: "npm link magic"
date: 2018-06-29T10:21:59+03:00
draft: false
description: Develop local node packages side-by-side
tags: [node, npm, nodejs, development, link, reload, watch, restart, open-source]
keywords: [node, npm, nodejs, development, link, reload, watch, restart, open-source]
---
Say you're developing two Node projects locally, where one ("the project") depends on the other ("the module"). An example could be a
components library and the client-facing UI of your platform.

With every change you'll make in your components library you'll need to publish it (`npm publish`),
then update your Frontend project (`npm update`/`npm install`). 

I know, you're probably using some sort of a continuous deployment mechanism that builds and packs the module for you. But even then you still
need to update the project with the module's current release version.    

That's too frustrating IMO...

<img style="min-width:80%;" src="https://media.giphy.com/media/aHnOjSIRfAz9m/giphy.gif" alt="Michael Jordan frustrated gif">

Today [Oleg](https://github.com/peroman86) thought me how the magic of [npm link](https://docs.npmjs.com/cli/link) saves the day!

#### Usage

We'll go straight to the example, explanation to follow.

1. Run `npm link` in the module’s folder:

```bash
$ cd ~/workspace/my-module
$ npm link
```

2. Run npm link <module_name> in the project's folder:

```bash
$ cd ../my-project
$ npm link my-module
```

![Michael Jordan Move](https://media.giphy.com/media/xT0GqjSBTImnHmfWMM/giphy.gif)

Removing the symbolic links to undo is super easy thanks to `npm unlink` built-in command.

1. Run `npm unlink --no-save <module_name>` in the project’s directory - removes the local symlink.

2. Run `npm unlink` in the module’s directory - removes the global symlink

#### Explanation

Running `npm link` in a module’s root directory creates a symbolic link from your global node_modules directory to the local module’s directory.    

Running `npm link <module_name>` in the project’s directory creates a symbolic link from ./node_modules/<module_name> to <global_node_modules>/<module_name>.

As a result any change you make in your required module will be immediately reflected in your project!

#### Pro Tip

You can actually do the same in one step:

```bash
$ cd ~/workspace/my-project
$ npm link ../my-module
```

![His Airness](https://media.giphy.com/media/l46CqLVMWzaJUFPLW/giphy.gif)
