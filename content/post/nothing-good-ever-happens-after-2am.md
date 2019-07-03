---
title: "Nothing Good Ever Happens After 2am"
date: 2019-07-03T14:24:15+03:00
description: A Postmortem session from Reversim Summit 2019
draft: false
images: [/images/reversim.jpg]
tags: [reversim, summit, conference, public-speaking, talk, session, postmortem, outage, incident]
keywords: [reversim, summit, conference, public-speaking, talk, session, postmortem, outage, incident]
---
![Reversim session](/images/reversim.jpg)


> It was a quiet Sunday at the office. We deployed an innocent looking change to some legacy code. We
were happy… for 24 hours. Then our support team got in touch to tell us about clients reporting an
issue. It was quickly linked to our, now notorious, patch."

These are the opening words of the abstract for [my talk](https://summit2019.reversim.com/session/5c6c2441d7ca690017a9d043) at [Reversim Summit](https://summit2019.reversim.com/).

As a regular participant, I was thrilled to hear that this year, the organizers introduced a new type of session: **Postmortems**.    
The opportunity to share the events of an infamous outage, as well as the mistakes leading to it, seemed like a unique and interesting experience.    
I chose a specific incident, which I thought would be both captivating and educational for other companies.


> What happened during the following hours is a tale of fellowship, accountability and positive intentions; but also one of SLA definitions we'd forgotten, oncall procedures we ignored and a revert plan we didn't have.

During the talk, I covered our outage procedure at [BigPanda](https://www.bigpanda.io/) - the roles and responsibilities we have, the incident priority definitions we set, the tools we use and the process we follow.     
I talked through the events and actions of the _"long night"_ while giving the participants beneficial company-agnostic takeaways.

## Takeaways
I strongly recommend watching the session recording (in resources), to understand the context.

### 1. Stick to the plan
During an incident, there's not much time to think. Most bureaucratic operations, such as communication to customers, should be executed almost automatically, according to the process.
### 2. Rule of thumb: REVERT FIRST
The number one priority is getting back to service while taking minimal risks. Frequently, that means rolling back the change that caused the issue. When working on complex deployments it is a good practice to prepare a revert plan.
### 3. Do not assume an outage
The Incident priorities were defined for a reason. An issue may look like an outage, and (support) sound like an outage, but might be just a bug.
Though easier said than done, take the time to estimate the impact and determine the suitable resolution efforts.
### 4. Time to call it a night
Incident mitigating endeavors tend to extend into the middle of the night. By that time, the team is probably exhausted and you may risk taking the wrong decisions or making avoidable mistakes.    
Sometimes stopping the work, _"calling it a night"_ and continuing from where you stopped the next day is the right path.
### 5. Do not commit to action items during an outage
Especially if you don't have a VP/Director of R&D, SRE or someone else to consult with beforehand.


## Resources
### The Slides
Can be found [here](https://www.slideshare.net/DanielKorn2/nothing-good-ever-happens-after-2am).
### Session Recording
Can be found [here](https://youtu.be/vueK_1Gm93c)

---

I'd like to thank [BigPanda](https://www.bigpanda.io/) for allowing me to openly speak about company internal procedures and encouraging me to speak about the incident.

Also, to thank the Reversim Summit [team](https://summit2019.reversim.com/about), for organizing a great conference, helping with dry runs, feedbacks, and logistics that made the speaking experience fun and memorable.

<p style="
  font-size: 12px;
  text-align: center;
  color: rgba(0,0,0,.68);">
  <img src="/images/HIMYM.jpg" alt="Nothing Good Ever Happens After 2am">
  <a href="https://www.pinterest.com/pin/326651779201355896/">https://www.pinterest.com/pin/326651779201355896/</a>
</p>
