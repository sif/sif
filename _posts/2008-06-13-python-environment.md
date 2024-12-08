---
layout: post
title: "Python Environment"
categories: python
tags: python
---

* TOC
{:toc}



## "Is it safe to delete \_\_pycache\_\_?"

Yes. You can even suppress the creation of these files. Ditto with **.pyc** and **.pyo** files. It's Python's bytecode.



##

```
python3 -m venv env

. env/bin/activate

deactivate
```

The dot operator is also called the source 

To fix your current installation, you need to find out if your pip installed packages were with --user or sudo:

```python
import site
site.getsitepackages()
site.getusersitepackages()
```

Run this in py2 and py3 to get their respective pip install locations. So, from now on, either use --user or a virtual environment. Never use sudo! Shame on pip developers for not making --user the default! As a matter of fact:

```
cd ~/
python3 -m venv env
cd myProject
ls ../env
../env/bin/pip3 install [desired module]
```

Or an alternative for the last line:

```
. ../env/bin/activate
```

To test that you are using the "right" python:

```
which python
```

The first time you do this, you should see it in /usr/bin/python or something like that. Now:

```
source ../env/bin/activate
which python
```

Now this should work for myProject.

Use diff to compare current and future Python setup:

```
pip freeze > ~/Desktop/installed.txt
pip -r ~/Desktop/installed.txt
```

If there is a need to reinstall pip:

```
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3 get-pip.py --force-reinstall
```

For an error like this: "/usr/local/share/doc/ghostscript is not writable."

```
sudo chown -R `whoami` /usr/local/share/ghostscript
```

Wrote this a while back: “Do this for all new Mac install: `sudo easy_install pip`”

Don't do this. Instead, for new installs, `brew install python` and `brew install python3`. Speaking of which, use virtual environment!

To raise recursion limit:

```
import sys

sys.setrecursionlimit(n)
```
