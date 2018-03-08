---
title: "Migrate Global Packages"
date: 2018-03-08T17:29:06+02:00
draft: false
description: Migrating global npm packages between node versions, using nvm
tags: [nvm, node, npm, nodejs, migration, packages]
keywords: [nvm, node, npm, nodejs, migration, packages]
---
Recently I moved to Node 8, which brings some new features you can read about [here](https://nodejs.org/en/blog/release/v8.0.0/).

I've been using [nvm](https://github.com/creationix/nvm) as my Node Version Manager for quite some
time and have only good things to say about it.

Today, while editing a `README.md` I wanted to use markdown-live (which I wrote about [here](https://danielkorn.io/post/markdown-live/)) before I noticed the package isn't available. 

Thanks to my awesome team lead [Erik](https://twitter.com/erikzaadi), I learned it is possible to migrate global npm packages between
Node versions, both while and after installing a new version, using the following `nvm` command:

```
$ nvm install 8 --reinstall-packages-from=6
```

You can also use:
```
$ nvm install node --reinstall-packages-from=node
```
which according to the docs will

> first use "nvm version node" to identify the current version you're migrating packages from. Then it resolves the new version to install from the remote server and installs it. Lastly, it runs "nvm reinstall-packages" to reinstall the npm packages from your prior version of Node to the new one.

![migrate global packages](/images/migrate-packages.jpg)

