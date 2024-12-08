---
layout: post
title: "Network Security Success Guide"
categories: nyu
tags: nyu ta
---

## Intro

I appreciate the opportunity given by <a href="http://damonmccoy.com">Damon McCoy</a> for me to be a TA for Network Security in <strong><em>Fall 2017</em></strong> (CS6823/CS3933).

<ul>
<li><a href="https://github.com/sif/sif/raw/main/files/CS6823%20Syllabus.pdf">Syllabus</a></li>
<li><a href="https://drive.google.com/file/d/1ZWxUngKIxiyANBfbhTRqVJbmvXd6A103/view?usp=sharing">CS6823_F2017_1.pptx</a></li>
</ul>

The prerequisite for this course is Computer Networking (CS6843). It seems that the class is taught a bit differently every semester. So, if you're a student and have trouble accessing Piazza, email me.

In addition to the classwork, I wanted to provide my own set of writing which I think will be really helpful, at least if nothing else, by reinforcement.

By the time you finish this course, you should have a broad idea of attacks and threats out there for computer networks. When you finish, you should know all of the stuff written in the knowledge nuggets. In addition to that:
<ul>
<li>network mapping, port scanning, sniffing</li>
<li>DoS, DDoS, reflection attacks, attacks on DNS, leveraging P2P deployments for attacks</li>
<li>cryptographic topics (relevant to network protocols) usch as block ciphers, stream ciphers, public key crypto, RSA< Diffie Hellman, CA (certificate authorities), digital signatures, message integrity</li>
<li>PGP, SSL, IPsec, wireless security protocols</li>
<li>firewall, IDS</li>
</ul>
List also doubles as a TODO.

## Knowledge Nuggets

This is a collection of stuff I think will be useful to current students (and maybe future students) taking the class. One thing I've noticed is that a lot of students had trouble with Linux and Python. Because this course teaches network security by using libs like scapy, basic Python knowledge is needed.

Here is what I think you need to do to be successful in this course. You may already have a Linux flavor installed or you already have Python installed. If so, you can skip to "Collection."

What you need to do now is to install Python then learn how to program in it. It's as close to pseudocode as it gets. I recommend setting up a virtual environment and call it "netsec" or something.

There is no official scapy for Python 3, so any installation will be for 2 anyway. So pip, not pip3. If you really want to use Python 3, email me so I have an idea of how many people actually want to setup scapy for Python 3. Otherwise it's not worth the effort on top of all your other course works.

If you use macOS, you should be fine. If not, almost any Linux flavor with VirtualBox will do if you need to use Windows for whatever reason. Python comes with macOS and most Linux. Either way, knowing how to do this is useful even if you don't like macOS or Linux.

### Collection

I call this part the "collection of knowledge nuggets." If you can think of a better name, feel free to write me. I always welcome advice and suggestions. Just a few quickie. If I'm missing anything or there is something you want to know about, let me know. I generalized my writing here, so it's usually applicable outside of the course as well. I may use vendor-specific terminologies (like from Cisco) because of its prominence.

<h6>Table of Content</h6>
<ol>
<li><a href="09-01-2017a.html">Part A</a></li>
<li><a href="09-01-2017b.html">Part B</a></li>
</ol>
