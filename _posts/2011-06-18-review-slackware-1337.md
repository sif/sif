---
layout: post
title: "Review: Slackware 13.37"
categories: slackware
tags: slackware review linux firefox fluxbox kde hal
---

About two months ago Pat finally released Slackware 13.37. I started using 13.37 as soon as it was released it and I have to say, I think I love this version more than any other Slackware versions. I usually keep my computer on 24/7 and run a few services and that gave me some insight.

If you're like me, you didn't bother reading the changelog or announcement. You just downloaded and upgraded as soon as you could (after you made your backups right?). You will notice a few things if you are upgrading from previous Slackware versions.

Apparently this is important to a lot of people. Firefox got upgraded to 4.0.1. There are a few known vulnerabilities for <a href="http://www.mozilla.org/security/known-vulnerabilities/firefox40.html" title="Security Advisories for Firefox 4">Firefox 4</a> that was quickly announced and fixed.

Now for what is important to me. If you have a poor-performing computer - Fluxbox pretty much stayed the same. If you don't mind the bloat, KDE got upgraded to 4.5.5. Actually it's not bloated, but I just don't feel like arguing right now and went with what seemed to be the popular view of KDE. To select either Fluxbox or KDE, hit up the console and type in: xwmconfig

You'll notice there are other options like WindowMaker and Xfce. At the moment I like Fluxbox and KDE so they were the only one I felt worth mentioning. One of the popular desktop environment is Xfce so you can definitely try that too. Whatever you select, it'll start that when you startx.

I have been reading about how the KDE team wants KDE to become free of HAL. I have no idea why but I am hoping that it does not affect Slackware too much in such a way that the Slackware team remove KDE from future Slackware release because of it.

Actually KDE would be most likely be forced to be removed from future Slackware release if KDE breaks free of HAL dependency. I hope Pat is prepared. The way I see it is that HAL works and I have not found anything that might suggest HAL to be obsolete.

If you are fortunate and lucky enough to have time to mess with the kernel, the kernel received a big upgrade from 2.6.33.4 to 2.6.37.6. As usual, there are two kernels in Slackware - huge and generic.

I highly recommend Slackware 13.37. <a href="http://store.slackware.com">Get it here!</a>
