---
layout: post
title: "Ethical Hacking"
categories: cybersecurity
tags: cybersecurity enterprise_risk_management risk_assessment
---

* TOC
{:toc}

<img src="https://github.com/sif/sif/raw/main/files/post_files/cia.png" />

https://github.com/Hack-with-Github/Awesome-Hacking

***ALE = SLE * ARO***

***SLE = AV * EF***

- annualized loss expectancy (ALE)
- single loss expectancy (SLE)
- annual rate of occurrence (ARO)
- exposure factor (EF)
- asset value (AV)



- Standards, used to achieve consistency
- Baselines, used to set minimum security level necessary
- Guidelines, used to set flexible recommended actions
- Procedures, used to detail step-by-step actions



Phases in penetration testing:

- Reconnaissance
  - Footprinting
- Scanning and Enumeration
  - Banner Grabbing (listed in Scanning but belongs in Enumeration)
- Gaining Access
  - Escalation of Privileges
- Maintaining Access
- Covering Tracks

Don't mix reconnaissance with scanning and enumeration. Reconnaissance is nothing more than steps taken to gather evidence and information on the target. It can be active or passive. 

Attack Types

- OS
- App level
- Shrink Wrap - off-the-shelf scripts and code
- Misconfiguration



## Access Control Mechanism

Common Criteria

- EAL (Evaluation Assurance Level)
- TOE (Target of Evaluation)
- ST (Security Target)
- PP (Protection Profile)



## Penetration Testing

There are three general phases to penetration testing. Preparation, assessment, and conclusion.

- Preparation: contract, scope, time
- Assessment: security evaluation or conduct phase, when the actual assault takes place
- Conclusion: final reports prepared for the customers

Three tests: black box, white box, gray box

Scanning Methodology

- Check for live systems.
- Check for open ports.
- Scan beyond IDS. (Basically avoid detection by IDS.)
- Perform banner grabbing.
- Scan for vulnerabilities.
- Draw network diagrams.
- Prepare proxies.

Internet Control Message Protocol (ICMP) is in every TCP/IP-enabled devices

<img src="https://github.com/sif/sif/raw/main/files/post_files/icmpmessagetype.png" />

Focus on Type 3 messages and Code 13 (this one lets you know the firewall is poorly configured, preventing delivery of ICMP packets).

A nonresponse to ICMP does not necessarily mean host isn't alive. It simply means it won't respond to ICMP.

ping

ping sweep

All port scanners work on the Transport layer.

Port Scan Types

- Full connect, easiest to detect but also most reliable
- Stealth, also known as half open scan or SYN scan, no three-way handshake is completed
- Inverse TCP flag, this uses FIN, URG, or PSH
- XMAS, named because all flags are used, which lights up like a Christmas tree
- ACK flag probe

**Inverse TCP flag** This scan uses the FIN, URG, or PSH flag (or, in one version, no flags at all) to poke at system ports. If the port is open, there will be no response at all. If the port is closed, an RST/ACK will be sent in response. You know, the *inverse* of everything else.

XMAS does not work on Windows machines because Windows machine are not RFC 793 compliant

UDP scan works by sending a datagram to see what you get in response. Because there is no handshake, if the port is open, you won't receive a thing back but if the port is closed, you'll receive an ICMP port unreachable message.

<img src="https://github.com/sif/sif/raw/main/files/post_files/networkscantypes.png" />

UDP ports are often utilized by malware.

The slower the scan, the better

Emphasis on nmap

<img src="https://github.com/sif/sif/raw/main/files/post_files/nmapswitches.png" />

-T3 is the default speed

- "s" is for scans
- "P" is for ping
- "o" is for output
- "T" is for speed and stealth (serial takes the longest time)



## Avoiding Detection

Nmap scan through Tor

Avoid scanning 129.51.0.0, 129.63.0.0, 128.50.0.0, etc. Look up "IP addresses you shouldn't scan".

One way to avoid detection by IDS is to fragment packets



## Windows

Majority of targets will likely be Windows

SID (security ID)

RID (relative ID)

Found in: C:\Windows\System 32\Config\SAM

Linux equivalent:

UID (user ID)

GID (group ID)

Found in: /etc/passwd



## NetBIOS

<img src="https://github.com/sif/sif/raw/main/files/post_files/netbioscodes.png" />

NetBIOS name resolution doesn't work on IPv6



## SNMP

Simple Network Management Protocol consists of a manager and agents, much like a dispatch center

The agents respond to the requests by going to the Management Information Base (MIB) and its data are arranged with numeric identifiers called OID (object identifier) 

Packet is known as SNMP GET

Configuration change is known as SNMP SET

Two types of managed objects:

- scalar
- tabular

LDAP

Connects to TCP port 389 to a Directory System Agent

The request queries a hierarchical/logical structure and returns a Basic Encoding Rules (BER)

NTPv3 and SMTPv3 provide both authentication and message integrity

SMTP commands: VRFY (validates user), EXPN (provides the actual delivery addresses of mailing lists and aliases), RCPT TO (defines recipients)


