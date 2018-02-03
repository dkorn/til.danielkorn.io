---
title: "Fingerprint sudo"
date: 2018-02-03T18:59:22+02:00
draft: false
description: Use the Touch Bar & Touch ID to sudo
tags: ["sudo", "macbook-pro", "fingerprint", "touch-bar", "touch-id", "permissions"]
---
If you're a MacBook Pro user with Touch Bar and Touch ID, this one's for you.

Add this line to the top of /etc/pam.d/sudo:

```shell
auth sufficient pam_tid.so
```

and start using your fingerprint to `sudo`!

**MIND BLOWN**, I know...

![Mind Blown!](https://media.giphy.com/media/l0MYEqEzwMWFCg8rm/giphy.gif)
