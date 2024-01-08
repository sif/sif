---
layout: post
title: "Vector Linux 5.8 SOHO (final)"
categories: vector_linux
tags: vector_linux
---

VectorLinux 5.8 SOHO (final) === Slackware 11.0.0, Kernel v2.6.20.3 SMP

Do `./configure --prefix=/usr` for all install unless noted.

/usr is where all the programs should be located at.

Don't use "Desktop Settings Wizard," it's trash.

## Mounting

Check to see if ntfs-3g is installed for Windows mount support.

Support for MuVo2 must be done in fstab and be treated as a mounted system. Like so: `/dev/sda /mnt/muvo auto defaults,user,noauto 0 0`

In order to charge MuVo2, `eject /dev/sda` and look for the charger icon to verify. It should be blinking.

## Patching

So, here is how to patch VectorLinux 5.8 and I think it works for other versions too. Get gslapt if it is not already there.

[Patch repository is in here.](ftp://ftp.osuosl.org/pub/vectorlinux/veclinux-5.8/patches/) Personally I have my local patch repository relocated into: `$home/.backup/patch/`

Be sure to double check the patches before doing any upgrades. Sometimes you might not even want to do the patching.
