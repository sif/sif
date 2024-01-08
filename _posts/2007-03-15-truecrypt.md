---
layout: post
title: "TrueCrypt"
categories: truecrypt
tags: truecrypt
---

* TOC
{:toc}

##



At the time of this writing, in order to configure wxWidget for TrueCrypt to use, you must extract wxWidgets-2.8.8.tar.gz and do the following:

```
mv wxWidgets-2.8.8 /usr/src/wxWidgets
make WX_ROOT=/usr/src/wxWidgets wxbuild
```


