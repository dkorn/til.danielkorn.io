---
title: "Event Sourcing & CQRS"
date: 2018-02-08T17:36:41+02:00
draft: false
description: Lessons Learned From Event Sourcing Talk
tags: ["event-sourcing", "cqrs", "data", "crud", "consistency", "talk"]
---
Today, [Tomer Gabel](@tomerg) gave a talk to [BigPanda](https://bigpanda.io/)'s RnD with the title: "An Abridged Guide to
Event Sourcing".    
This eye-opening presentation definitely deserves a more in-depth blog post, but I figured it might be
useful to summarize my takeaways from it.

_Disclaimer: the ideas and takeaways mentioned reflect my understandings of the lecture, and not necessarily the speaker's original intents._

#### Terminology
* Event Sourcing - each entity in our DB is a stream of immutable events
* CQRS - separation of writes (append events) and reads (adjustable projections)

> Who told you you’re allowed to destroy data?
-- Greg Young

#### Lessons Learned
* CRUD shouldn't be a premise. Strong consistency isn't always required
* Storage costs is an operational concern that's worth discussion
* Event Streams + CQRS (done right) has several pros like decoupled reads/writes and built-in
  auditing which helps with debugging
* Using Snapshots is a great way to improve performance

#### Resources
Further reading, if I somehow managed to intrigue you

* [Talk slides](/event_sourcing_slides.pdf)
* [Recording](https://youtu.be/AvRnY9pDmSw) from Reversim conference

![Interesting](https://media.giphy.com/media/eKDp7xvUdbCrC/giphy.gif)
