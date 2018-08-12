---
title: "Open Sesame"
date: 2018-08-12T23:20:47+03:00
draft: false
description: Open the project's last build view in Travis CI web interface from the terminal
tags: [cli, travis, CI/CD, continuous-integration, continuous-delivery, build, terminal-tricks]
keywords: [CLI, Travis, CI/CD, Continuous Integration, Continuous Delivery, Build, Terminal Tricks]
---

In the company I work for, [BigPanda](https://www.bigpanda.io/), we use [Travis CI](https://travis-ci.org/) for our CI/CD process.

After every Git push to one of our projects' branches, a new build is triggered. The build usually includes test suite run and creation of the artifact to be deployed (I know, we're
not continuous deployment fully-automated yet).

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/deliver-continuously1.png" alt="Deliver Continuously MEME">
  Image Source <a href="http://www.softwarearchiblog.com/2016/11/ci-cd.html">Software Archiblog</a>
</p>

Though our trusted Slack bot notifies for every build results in a dedicated channel, I often find
myself in need of opening Travis' web application, to go over the log, debug or restart the build.

**Today I learned** how to prompt the last project build view in the Travis web interface, using
[Travis CLI](https://github.com/travis-ci/travis.rb) (client).

#### Usage

Once installed and configured all you have to do is type the following in your repo's dir:

```
$ travis open
```

and a new browser tab will pop up.

You can also just print the URL with the `--print` option, or open the repo in GitHub with the `--github` flag.

If you're interested in a specific build or job, append its' number to the command.    

The best way I found to get the number of your branch last build is: 

1. Run:

    ```
    $ travis branches
    ```

    This will output the most recent build for each branch.

2. Locate your branch last build number (say `17`).

3. Run:

    ```
    $ travis open 17
    ```


TBH, I haven't played with the client enough to list pro tips and advanced use cases.    

If you know useful tricks go ahead and share them in the comments section below.
