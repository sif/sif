---
layout: post
title: "My CTF Experience With INT 0x80"
categories: ctf
tags: defcon ctf
---

I couldn't think of a funny title so I went with what you see now. "Fun Time With INT 0x80" sounded off. Anyway.. I just wanted to share my experience.

I learned a lot and I want to thank the following for the experience: Robin (Captain), potkettleracism, theorycrafter, jy200, banksy, Jayjay, 0x00, BugCatcherNade, RubberBanned, victorlvg678, soap, minceontoast

I was able to reproduce some of what we did and would do something like this again. This DEFCON was hosted by Threat Sims. The top 20 would go on to the finals and we were ranked 39. Very close.

This year was a bit different because of the pandemic. This was all done online as opposed to in-person. Challenges would open up at some scheduled time. I personally enjoyed Programming and Trainer challenges the most.

In addition to the two categories I just mentioned, there are remote code executions, forensics, OSINT (open source intelligence), crypto, and meme based challenges.

The team members are talented people with a passion for learning about security. For example, potkettlerracism is a moderator r/lockpicking and a security engineer. (He goes by the same name on the sub.)

The initial discoveries that set off the race were made by potkettleracism when he found Initech and Michael Bolton's information on LinkedIn. You just need to look at their about page, resume, and other relevant information.

RubberBanned is another talented member who is simply handsome. The theme of the CTF, at least for one portion of it was Office Space and that movie was "required viewing" prior to the competition.

Many of the programming challenges is simply being smart about how you brute force the solution and automating the process. The first and second Ping Pong challenge shows this.

You are given a letter and must mirror this back. My initial response was to try this out first and look for a pattern. I tried to use subprocess and other Python generic (for the lack of a better word) library before I was told that Pwnlab would do what I wanted, which is to talk to the machine you are trying to break.

Jayjay would show that a lot of the challenges are simply a matter of experience. "All about that base" is an example where you are given a string and nothing more. If you did not have any experience, you would have had to looked it up and spent a few hours.

For that crypto challenge, all you had to simply do was plug it in a base64 calculator.

In the future with more practice, as long as each member continue to grow in the area of strength, we can only get better. It didn't help that during the week, I had power outage and was unable to fully prepare but there is always a next time. Thanks for reading!

Originally published at: [My CTF Experience With INT 0x80](https://medium.com/@cassandriel/my-ctf-experience-with-int-0x80-8668c7cdf3ff)
