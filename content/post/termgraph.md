---
title: "Termgraph"
date: 2018-12-13T23:12:14+02:00
draft: false
images: [/images/termgraph-stars.png]
description: Command line tool for simple terminal graphs 
tags: [terminal-tricks, cli, command-line, graphs, bar, python]
keywords: [Terminal Tricks, CLI, Command Line, Graphs, Bar, Python]
---
A few months back I needed a terminal charting tool to quickly create a simple graph.

We had a recruiting competition in [BigPanda](https://bigpanda.io/), and I wanted to draw a bar graph in my terminal to
display the employees' leaderboard.
I ended up using the powerful yet complicated [gnuplot](http://www.gnuplot.info/), a task which took
longer than I expected.

_**Today I learned**_ about [Termgraph](https://github.com/mkaz/termgraph), a Python-based command
line tool to draw simple terminal graphs.

### Usage

1. Create the data file
    * Two or more columns `,` or `space` separated. The first column is the label and the rest
      are the numbered values (at least one)
    * To add categories write `@` followed by the category labels.
    
2.  Execute the command:
   ```
   $ termgraph <data-file> <options>
   ```

### Example

Let's say we wanna draw a graph of a Git project commit leaderboard. To list the contributors by the number of commits, see my [previous post](https://danielkorn.io/post/commit-leaderboard/).

This is how the data file[1] will look like:
```bash
$ cat leaderboard.dat

erikzaadi,51
dkorn,46
Guy Perkal,5
peroman86,8
Spyes,4
Tal Kimhi,1
pinikeizman,3
```

And all we need to do is run:
```bash
$ termgraph --title "Sentinel Commit Leaderboard" leaderboard.dat --format '{:.0f}'

# Sentinel Commit Leaderboard

erikzaadi  : ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 51
dkorn      : ▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇▇ 46
Guy Perkal : ▇▇▇▇ 5
peroman86  : ▇▇▇▇▇▇▇ 8
Spyes      : ▇▇▇ 4
Tal Kimhi  : ▏ 1
pinikeizman: ▇▇ 3

```

Notice I used the `--title` option and `--format '{:.0f}'` to display integers, there are many other eye candies[2] to play with.

The coolest one IMO is the `--custom-tick` option which allows emojis!

```bash
$ termgraph --title "Sentinel Commit Leaderboard" leaderboard.dat --format '{:.0f}' --custom-tick '🐙'

# Sentinel Commit Leaderboard

erikzaadi  : 🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙 51
dkorn      : 🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙🐙 46
Guy Perkal : 🐙🐙🐙🐙 5
peroman86  : 🐙🐙🐙🐙🐙🐙🐙 8
Spyes      : 🐙🐙🐙 4
Tal Kimhi  :  1
pinikeizman: 🐙🐙 3
```

### Installation

Using [PyPI](https://pypi.org/project/termgraph/)

```
$ pip3 install termgraph
```

[1] For more complex data file examples check out [this dir](https://github.com/mkaz/termgraph/tree/master/data) in the project GitHub repo.

[2] Use colors:

<img src="https://user-images.githubusercontent.com/45363/43405623-1a2cc4d4-93cf-11e8-8c96-b7134d8986a2.png" width="655" alt="Multi variable bar chart with colors" />

Stack the data

<img src="https://user-images.githubusercontent.com/45363/43405624-1a4a821c-93cf-11e8-84f3-f45c65b7ca98.png" width="686" alt="Multi variable stacked bar chart with colors" />

Calendar Heatmap

<img src="https://user-images.githubusercontent.com/45363/43405619-1a15998a-93cf-11e8-8a3f-abfd2f6104a5.png" width="596" alt="Calendar Heatmap" />
