---
layout: post
title: "Network Security"
categories: cybersecurity
tags: cybersecurity CDN
---

* TOC
{:toc}

https://firebog.net

https://dangerousip.blogspot.com



## Network Segmentation and Isolation

https://en.wikipedia.org/wiki/Air_gap_(networking)

jump server, jump host, jump box



## Router

https://routersecurity.org

Turned off UPnP

Turned on "Always Use HTTPS to Access Router"



## WiFi

https://www.yahoo.com/news/turn-off-household-appliance-want-152900100.html
- Turn off microwave oven
- Use video calling at less popular times if possible
- Use ethernet when possible
- Don't put router near devices that might interfere with it
- Disconnect devices when not in use

Use complex passwords for WiFi



### Wireless Charging

Wireless charging sucks, they damage the battery permanently at a faster rate



## LAN

- Don't let anyone in the LAN, if they must, have them use the guest account
- IoT devices must be on guest wifi if you can't create a separate intranet, otherwise IoT devices can see other devices like your NAS



## Firewall

A system designed to control incoming and outgoing network traffic

"Close port 8080 on every computer you ever repair. That'll make sure it STAYS repaired."



## Intrusion Detection System



## Intrusion Prevention System



## Reverse Proxy

"A reverse proxy accepts a request from a client, forwards it to a server that can fulfill it, and returns the server’s response to the client."
https://www.nginx.com/resources/glossary/reverse-proxy-vs-load-balancer/



## Content Delivery Network

Often used to deal with DDoS

Also known to provide WAF (web application firewall) and WAN (wide area network) optimization



### Cloudflare

Cloudflare is a reverse proxy that allows traffic to pass through it
Cloudflare focuses more on security



### Akamai

https://www.akamaistatus.com/

Customer <-> Akamai <-> Application

"Akamai maintains a global network of more than 240,000 'edge servers'. These are positioned at the 'edge' of the Internet, as close to end users as possible."



#### Kona

WAF

Network and application layer security suite inline before Ion edge servers and applications



#### Ion

The Akamai edge content delivery network



### CloudFront

CloudFront is owned by Amazon, easy to confuse with Cloudflare
CloudFront is an actual server that delivers content from edge servers



### EdgeCast


