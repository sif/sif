---
layout: post
title: "Nessus vs Nmap"
categories: network
tags: vulnerability_scanner network_scanner penetration_test 
---

Before trying to assess your network security, you need to take stock of what you have. The two most common tools you can start out with are Nessus and Nmap. Nmap is a network scanner while Nessus is a vulnerability scanner.

Nmap is generally much more straightforward as it's a CLI tool. To open up Nmap, you simply write `nmap` and the desired options and target. Nessus is web-based. Once you start it, you open it up on localhost and the port it's opened up on.

In general, you start with Nmap to figure out what devices are on your network. Then you run Nessus to see what vulnerabilities are on these devices. Nmap is open source so it is more robust. Nessus depends on updates and extensions to expand its capabilities. With Nmap, it allows you to write scripts if you needed more from it.

For example, during a penetration test, you might run something like: `nmap -sn -n 192.168.1.0/24`

This will scan for devices on the network. Let's say there is a device at: 192.168.1.50

You can input that IP and run a scan. Nessus can find a lot of vulnerabilities from simple things like default passwords and setup to missing security patches. At this point, you can start looking at tools that focuses on specific web applications or devices. 

For example, you could look at Nikto which focuses on web servers. You can also look at other alternatives just in case you feel Nessus may have missed something, like OpenVAS. 

As long as you use the right tool for the right problem, you'll be able to address most problems.
