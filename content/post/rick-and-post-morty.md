---
title: "Everyday Engineering Lessons Learned from 'Rick and Morty'"
date: 2020-01-18T21:03:57+02:00
draft: false
description: Summary of the talk "Rick and (post)Morty", given at DevOpsDays TLV 2019
images: [/images/rick_and_post_morty.JPG]
tags: [devopsdays, summit, conference, public-speaking, talk, session, rick-and-mortyi, mentoring,
blameless-postmortems]
keywords: [DevOpsDays, summit, conference, public-speaking, talk, session, Rick and Morty,
mentoring, Blameless Postmortems]
---
<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/rick_and_post_morty.JPG" alt="Rick and (post)Morty DevOpsDays 2019">
  Rick and (post)Morty, DevOpsDay TLV 2019
</p>

During [DevOpsDays TLV 2019](https://devopsdaystlv.com/), my partner in crime [Erik Zaadi](https://twitter.com/erikzaadi) and I gave a talk with the title ["Rick and (post)Morty"](https://devopsdaystlv.com/talk/rick-and-postmorty/).

What started as a joke a few months before the conference, turned out to be the most enjoyable presentation I have ever given.

The talk enabled us to combine three of our greatest loves: 

1. Software Engineering
2. The genius animated science fiction sitcom Rick and Morty
3. Using numerous MEMEs and GIFs

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/20_minutes_adventure.jpeg" alt="20 Minutes Adventure MEME">
  <a href="https://knowyourmeme.com/memes/20-minutes-adventure">20 Minutes Adventure</a>
</p>


### Rick and Morty and Engineering: wait, what?!

In case you haven't watched the show, [Rick and Morty](https://en.wikipedia.org/wiki/Rick_and_Morty) is an American adult animated science fiction sitcom, created by Justin Roiland and Dan Harmon.    
The series follows the misadventures of cynical mad scientist Rick Sanchez and his good-hearted but fretful grandson Morty Smith, who split their time between domestic life and interdimensional adventures.

Putting cynicism aside, we feel that if you look past the crazy animation and bad language, and open your eyes, there's a lot to learn about life from this TV show.    
The talk focused on the Engineering lessons we learned.

Disclaimers

- We are not Rick and Morty experts
- The opinions represented here are our own
- This post will not spoiler season 4

Throughout the talk, we tried to think about Rick and Morty as people we meet in our day2day work.

#### Rick

Senior principal staff AI architect, who does not and will not have a LinkedIn profile.    
He still writes Cobol and can configure Kubernetes without using any YAML files. No one knows how long he's been in the company, and the general rule is that Rick will know how to do anything.    
He's known to be unapproachable, rude, condescending and won't speak with anyone from HR.

![Rick fake twitter account](/images/rick_twitter.png)

#### Morty

A 2nd-year student that got lucky and grabbed an intern position.    
He thinks he has a lot of potential and considers himself a hard worker.     
Morty did docker tutorial, however, he doesn't understand how everyone became an expert by doing so.

![Morty fake Linkedin](/images/morty_linkedin.png)

---

### Takeaways
While we strongly encourage you to watch the show itself, the lessons listed are relevant even If you haven't done so.

Here's a summary of the insights we shared. For complete context, go watch the [full talk](https://youtu.be/TktyDcxcbyk) from DevOpsDays conference.

#### TL;DR

1. Do one thing and do it well
2. Start small and build-up
3. Deal with it
4. Scale-out isn't always the answer
5. Practice Blameless Postmortems
6. Avoid side effects
7. Know when to call it a night and start fresh
8. The importance of Mentoring


#### 1. DOTADIW - Do One Thing And Do It Well    
**Season 1 Episode 9 - _"Pass the butter"_**

> "This is the Unix philosophy: Write programs that do one thing and do it well…" [Doug McIlroy](https://en.wikipedia.org/wiki/Douglas_McIlroy)

We've all been there, we start with a simple script that automates a single operation. Soon enough
another need arise and we, almost naturally, tend to just add it into our original script, often by
creating a code smell. After a few more iterations, our code is loosely related, complex and non-maintainable.

Resist the temptation of having an all-in-one piece of code. Write programs that **do one thing, and do it well**.

#### 2. Start small and build-up
**Season 3 Episode 3 - _"Pickle Rick"_**

No matter how large and complex the feature you're handed, break it down into feasible milestones, that build upon each other as building blocks.

Overcome any obstacle by starting small and building up, be lean and work with what you got.

#### 3. Deal with it
**Season 3 Episode 3 - _"Pickle Rick"_**

Ignoring matters outside of your comfort zone, won't make them go away.

If you're trying to avoid that uncomfortable feedback session or even a salary discussion, deal with it instead of turning yourself into a pickle!

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/pickle_rick.jpeg" alt="Pickle Rick">
  <a href="https://www.inverse.com/article/35362-rick-and-morty-pickle-rick-dan-harmon-concept-art-designs">Pickle Rick!</a>
</p>

#### 4. Scale-out isn't always the answer
**Season 1 Episode 5 - _"Meeseeks and Destroy"_**

While Scale-Out has many advantages, it's worth remembering that it isn't the answer to overcome every engineering boundary. Sometimes there are other limitations like application logic, network, and data distribution.

[Scale-out](https://www.techopedia.com/definition/31678/scale-out) comes with a price - it requires re-thinking the architecture of the app and in some scenarios even changing the source code.

It may sound obvious, but choose scale-out only when it's the right path and doesn't over-engineer simpler solutions.

#### 5. Blameless Postmortems
**Season 1 Episode 5 - _"Meeseeks and Destroy"_**

Practicing Blameless Postmortems is an effective way to truly learn from major incidents and outages, without any blame games.

The general postmortem format is as follows - bring the team together to take a deeper look at an outage, figure out what happened, why it happened, how the team responded, and what can be done to prevent repeat incidents and improve future responses.    
On top of these, you **assume best intentions**, instead of identifying and punishing whoever screwed up. Participants don't need to worry about being fired or demoted

The focus is on improving performance moving forward, decrease the chances of ignoring incidents for fear of blame and creating an open, always-improving culture of learning.

The next time you start a postmortem - remind all the participants that there's no room for finger-pointing and blame games.

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/blameless_postmortems.gif" alt="Blameless Postmortems">
  <b>Blameless Postmortems</b>, Rick and Morty S01E05 "Meeseeks and Destroy"
</p>

#### 6. Avoid side effects
**Season 1 Episode 6 - _"Rick Potion #9"_**

Avoiding side effects within the functions in our codebase makes them more predictable and less dependent on the state of the system. A function without side effects can execute anytime, and will always return the same result, given the same input.

The same applies to immutable infrastructures, in the Ops context. Having immutable infrastructure means more consistency and reliability, and a simpler deployment process. 

Side effects free code and infrastructure will prevent you from Cronenberged mutations.

#### 7. Know when to call it a night and start fresh
**Season 1 Episode 6 - _"Rick Potion #9"_**

If you find yourself battling production issues into the middle of the night, doing patch upon patch, it's probably a good time to stop and **_call it a night_**.     
The risks you take when everyone is exhausted, as well as the burnout, might not worth the gain.

**_Start fresh_**, whether it means to continue the mitigation on the following business day, or creating a new service or module when the spaghetti code you're trying to patch is too complex.

#### 8. Mentoring

Going back to Rick and Morty as people we meet at work, in a way, Rick being an experienced Senior is de facto mentoring Morty from their first adventure and in their daily life.

Here are some of our thoughts and insights on what it means to mentor:

- Mentoring a ride, filled with ups and downs.
- It's hard work, not rewarding at most times, taking every ounce of your patience.
- Sometimes as a mentor, you need to push your mentees to their limits. And that might boost their confidence and feeling of accomplishment
- You'd be surprised by how much a junior can teach a senior, it's more than a fresh set of eyes, it's another way of thinking, an approach that you didn't think of.
- Sometimes even the smallest gesture, just being there for her, can alter the mentees' reality.
- It'll help you and your organization mature, empower your people and spread knowledge.

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/batman_robin.jpg" alt="Batman and Robin Rick and Morty">
  Batman and Robin - Rick and Morty on <a href="https://whateverifitsfunnyme.tumblr.com/post/171622839340">tumbler</a>
</p>


The **talk Recording** can be found [here](https://youtu.be/TktyDcxcbyk).

The **Slides** can be found [here](https://www.slideshare.net/DanielKorn2/rick-and-post-morty-devopsdays-tlv-2019).

Co-authored and given with [Erik Zaadi](https://twitter.com/erikzaadi).
