---
layout: post
title: "Hackathons"
categories: cybersecurity
tags: cybersecurity hackathon contest contests ctf
---

* TOC
{:toc}



## picoCTF



## RangeForce



## Hack The Box

### Invite Challenge

1. First step, go here: https://www.hackthebox.eu/invite
2. Open up developer tools on your browser. Hit console. Read that hint there.
3. Look for inviteapi.min.js. Look at it.
4. In the console, type in "makeInviteCode()".
5. Take the output and stick it into a ROT13 calculator.
6. It'll tell you something about making a POST to some link. Do so: https://www.hackthebox.eu/api/invite/generate
7. Once you get that, decode it using a Base64 calculator.
8. Whatever you get, stick it into the invite field.

After you make your account, go to "Starting Point."



## [HackThisSite](https://www.hackthissite.org/)

HTS completed:

- Basic - 1, 2, 3, 4, 5, 6, 7
- Realistic - 
- Application - 
- Programming - 
- Logic - 
- Extbasic - 
- Javascript - 1, 2

The answers and what you need to know:

- Requirements: HTML
- Requirements: Common sense
- Requirements: Basic HTML knowledge
- Requirements: HTML knowledge, an email address (though an email address is not really required..)
- Requirements: HTML knowledge, JS or FF, an email address
- 8ea8d1d2
- grr.. talk about deceptive, use &&
- Requirements: Knowledge of [SSI](http://en.wikipedia.org/wiki/Server_Side_Includes) (dynamic html executed by the server, rather than the browser)

Trying:

```
<!--#exec cmd="ls -l"-->
```

I got:

"If you are trying to use server side includes to solve the challenge, you are on the right track: but I have limited the commands allowed to ones relevant towards finding the password file for security reasons(because there will always be that one person who decides to execute some rather nasty commands). So please manipulate your code so that it is a little more pertaining to the level."

Trying:

```
<!--#exec cmd="ls"-->
```

I got:

"Hi, tshngmww.shtml hipykpqu.shtml ztxdhjxn.shtml avpfeoie.shtml fviqpmaw.shtml kqbybdzc.shtml dzrnmzgx.shtml npcsygfl.shtml whqxxojt.shtml ylomcmvu.shtml uhdppswp.shtml gzntiicx.shtml dzwbqiuu.shtml qvzuieng.shtml smcerykh.shtml qjhnmhmq.shtml znodwztr.shtml!

Your name contains 254 characters."



## [Threat Sims](https://ctf.threatsims.com)

Ping Pong 2

```python3
from pwn import *

flag = b""

r = remote('164.90.147.2', 2346)
letter = r.recv()

while True:
    letter = r.recv()
    flag += letter
    print(flag)
    r.send(letter)

r.interactive()
```



## Others

- https://microcorruption.com/ Embedded
- https://overthewire.org/wargames/ General
- https://cryptopals.com Crypto
- https://www.stockfighter.io Finance
- https://www.starfighters.io Defunct
- https://nyhackathons.com Social
- https://crackmes.one Reverse Engineering
- https://canyouhack.us General
- https://trailofbits.github.io/ctf/ General



## Useful

- SANS SIFT
- Kali Linux
- SANS Slingshot
- Black Arch



### Forensics

log files, memory images, parts of OS

- Volatility
- Autopsy
- Sleuth Kit
- FTK Imager
- SANS SIFT



### Binary Exploitation

reverse engineer, identify flaws, exploit a service, mostly based on Linux so GDB

- pwntools
- GDB Enhanced Features
- Binary Ninja

exiftool

binwalk (-e to extract) a file if you believe there is a file within a file



### Data

parsing data, patching data, metadata

- GHex
- Hexed
- vi
- %!:xxd 
- Bless
- strings
- Exiftool
- Python "quick inline code like python -c ‘print “\x41\x42”’ is a great way to quickly construct data you need for exploits, network attacks or testing purposes"



### Networking

network captures

- Wireshark
- tshark
- scapy
- netcat
- nmap



### Web Application

modify XHR requests, POST data, query string parameters, header, cookie manipulation

- Burp Suite
- OWASP ZAP
- browser dev tools such as Console, Network, Application

If you encounter javascript, just put it in console and see.


