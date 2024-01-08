---
layout: post
title: "Solution Stack"
categories: solution_stack
tags: solution_stack
---

* TOC
{:toc}

## XAMPP

WAMP, LAMP (Linux, Apache HTTP Server, MySQL, PHP)

To downgrade PHP from 7.1.1 to 5.6:

1. https://sourceforge.net/projects/xampp/files/XAMPP%20Windows/5.6.36/
2. Download and extract xampp-win32-5.6.36-0-VC11.zip
3. Rename the php and apache folder present in C:\xampp to back them up
4. Copy the php and apache folder from the extracted zip file to C:\xampp
5. Add "C:" before \xampp\ to the php.ini file in the php folder
6. It is okay to start XAMPP now

```
sudo tar xvfz xampp-linux-1.7.3a.tar.gz -C /opt
sudo chown sif:users /opt/lampp/htdocs
sudo chown sif:users /opt/lampp/etc/php.ini
```

Reminder, if you are backing up, just backup the following:

- Backup databases.
- Backup all files in /opt/lampp/htdocs except the folders webalizer / xampp.



## MERN

- MongoDB
- Express.js
- React
- Node.js



## MEAN

- MongoDB
- Express.js
- Angular
- Node.js


