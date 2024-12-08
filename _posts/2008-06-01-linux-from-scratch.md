---
layout: post
title: "Linux From Scratch"
categories: linux
tags: linux
---

* TOC
{:toc}

https://www.linuxfromscratch.org

http://www.buildyourownlinux.com

<img src="https://github.com/sif/sif/raw/main/files/post_files/109_-_ljpvixf.jpg" />



## Sif 2008

The next set of things I needed to do to make it a daily driver was to assemble a team who can help me maintain the OS. I also needed: package manager, software repository (and mirrors), ISO packager

This was an interesting experience.

Up to: http://www.linuxfromscratch.org/hints/downloads/files/stages-stop-and-resume.txt

Last directory in: lfs:/mnt/LFS/sources/glibc-build$

http://www.linuxfromscratch.org/lfs/view/6.3/chapter05/adjusting.html

supposed to do this
```
gcc -dumpspecs | sed 's@^/lib/ld-linux.so.2@/tools&@g' \
  > `dirname $(gcc -print-libgcc-file-name)`/specs
```


