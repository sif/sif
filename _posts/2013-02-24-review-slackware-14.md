---
layout: post
title: "Review: Slackware 14"
categories: slackware
tags: slackware review
---

I might be late to the party but I'm here. Slackware 13.37 was fine for me but I wanted to have the "new" feeling so I decided to give Slackware 14 a shot. And I must say.. Slackware 14 is absolutely amazing in every sense of the word. Amazing doesn't even describe it, you really need a new word to describe it.

Pat and team did a seriously awesome job.

I need less and less packages to install at the beginning as new Slackware versions get put out. For example, I used to run compiz-fusion (now known as Beryl) and other desktop effects. No longer! KDE came out with something similar (since 13.37). New KDE means a more stable and smoother desktop effects.

It is hard for me to make changes to the initial desktop setup because it looks good out of the box already. The best part is that Slackware stays true to its root.

I ran into a little problem but it was quickly dispatched. I have a nvidia card. My install doesn't like nouveau.

What Slackware does is installs nouveau for you if it detects a nvidia card. Some people run into a problem with this. If you don't, you probably won't need to install the nvidia driver since you will have 3D acceleration. You will want to install the nvidia driver driver if nouveau causes you problems.

When you boot up and it just freezes either at something about RAID or about nouveau. Here is my suggestion: don't change anything just yet. Stay calm and take a deep breath. There is nothing wrong with your video card or RAID setup.

Just know that you can't have nouveau and nvidia drivers running at the same time. You need to blacklist nouveau. Remember what it told you to do after installation? It said to hit ctrl+alt+del to reboot. Right before you do that, do this:

```
touch /mnt/etc/modprobe.d/disable-nouveau.conf
vi /mnt/etc/modprobe.d/disable-nouveau.conf
```

Use emacs or vi. Now type this in:

```
blacklist nouveau
options nouveau modeset=0
```

Once you reboot you should be able to find and install the nvidia driver.

Go get Slackware 14 <a href="http://store.slackware.com">here</a>!
