---
layout: post
title: "Cleaning up KDE"
categories: kde
tags: kde linux
---

If you export your home to a new setup and the setup contains newer versions of KDE, you end up getting overlaps. That is, if you're lucky and don't run into any other problems.

For KDE3, the context menu is the most obvious. To fix it, just go to: `~/.kde/applnk/.hidden`

For KDE4, for recurring problems, I would just start from scratch. I usually don't even bother with themes now because it has caused too problems. Widgets are really hard to deal with and seriously not worth the effort for the time you will spend trying to recover it.

But in case your problem is limited in scope, just look in:

```
~/.kde/share/apps/<apps>
~/.kde/share/config/<apps>
~/.kde/share/config/plasma-desktop-appletsrc
```

It is `~/.kde` or `~/.kde4` depending on your flavor of Linux.
