---
title: "git push force with lease"
date: 2019-03-08T19:02:22+02:00
draft: false
description: Safely git push using the --force-with-lease flag 
images: [/images/force-with-lease.jpg]
tags: [git, push, force, force-with-lease, version-control, git-tricks]
keywords: [git, push, force, force with lease, version control, git tricks]
---
I try to avoid using git push `--force` option whenever possible.    
The reason is, it disables the check that verifies the remote ref is an ancestor of the local ref.    
This means that if someone else meanwhile pushed his/her work upstream, it will be overwritten by the
`--force` flag.

Having said that, there are some cases in which a force push is the only option, _or so I
thought_...

Today, during a PR best practices session by the incredible [Erik](https://twitter.com/erikzaadi),
I learned about the [`--force-with-lease`](https://git-scm.com/docs/git-push#Documentation/git-push.txt---no-force-with-lease) flag.

It eliminates the risk of overwriting a team member work, by refusing to update the remote ref if its' current value does not match our local remote-tracking branch.
The push will be rejected with `"stale info"` message, and we'll have to fetch the updates from
upstream and rebase first.

An analogy courtesy to git docs:

_"It is like taking a "lease" on the ref without explicitly locking it, and the remote ref is updated
only if the "lease" is still valid"_.

## Pro Tip

Add a git alias to easily use --force-with-lease whenever you need to push force:
```
$ git config --global alias.pushf "push --force-with-lease"
```

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/force-with-lease.jpg" alt="git force with lease meme">
  Source <a href="https://developer.atlassian.com/blog/2015/04/force-with-lease/">force-with-lease</a>
</p>
