---
title: "Kubectl Autocomplete"
date: 2018-12-18T18:25:21+02:00
draft: false
description: Autocompletion for kubectl in your shell
images: [/images/kubernetes.png]
tags: [kubernetes, kubectl, containers, autocomplete, zsh, bash, shell, fish, oh-my-zsh, cli]
keywords: [kubernetes, kubectl, containers, autocomplete, zsh, bash, shell, fish, oh-my-zsh, CLI]
---
Recently, we migrated our development environment from [Docker Compose](https://github.com/docker/compose) to [Kubernetes](https://github.com/kubernetes/kubernetes).

Kubernetes has a command line interface for managing its clusters called `kubectl`.

As you probably guessed from the title, **_today I learned_** how to configure autocompletion for
kubectl.

![Kubernetes Logo](/images/kubernetes.png)

## Setup

Depends on the shell you're using.

### zsh

Add the following to your `.zshrc` file:

```bash
source <(kubectl completion zsh)  # setup autocomplete in zsh into the current shell
echo "if [ $commands[kubectl] ]; then source <(kubectl completion zsh); fi" >> ~/.zshrc # add autocomplete permanently to your zsh shell
```

If you're using [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh) you can use this [plugin](https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins/kubectl) by adding `kubectl` to the plugins array in your `.zshrc`:

```bash
plugins=(... kubectl)
```

### bash

Add the following to your `.bashrc` or `bash_profile`:

```bash
source <(kubectl completion bash) # setup autocomplete in bash into the current shell, bash-completion package should be installed first.
echo "source <(kubectl completion bash)" >> ~/.bashrc # add autocomplete permanently to your bash shell.
```

### fish

[Shahar Kedar](https://twitter.com/shahar_kedar) pointed me to [this repo](https://github.com/evanlucas/fish-kubectl-completions).

## Pro Tip

If you haven't already, define this time-saving alias:

```bash
alias k="kubectl"
```
