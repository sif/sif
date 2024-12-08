---
layout: post
title: "Computer Networking"
categories: computer_networking
tags: computer_networking computer_network
---

* TOC
{:toc}

<img src="https://github.com/sif/sif/raw/main/files/post_files/osi.png" />

|    OSI    |    DOD    |
|:---------:|:---------:|
| Application, Presentation, Session | Process/Application |
| Transport | Host-to-Host |
| Network | Internet |
| Data Link, Physical | Network Access |



Three-way handshake: SYN, SYN/ACK, ACK



req - request
res - response

octet

virtual IP



Regional Registry Coverage Map

ARIN
LACNIC
AFRNIC
RIPENCC
APNIC



ifconfig:
inet addr:10.0.0.130  Bcast:10.0.255.255  Mask:255.255.0.0

route:
10.0.0.0        *               255.255.0.0     U     0      0        0 eth0
127.0.0.0       *               255.0.0.0       U     0      0        0 lo

Notice, no gateway, means no internet. Only can work with others in the local network. As such you can add a gateway to connect it to the internet. A gateway that is already connected to the internet that is.

To turn on:

```
/sbin/route add default gw 10.0.0.1
/sbin/route
```

To delete:

```
/sbin/route del default
```

Another way to turn on the gateway:

```
/sbin/ifconfig eth0 10.0.0.252 netmask 255.255.0.0
/sbin/ifconfig eth0
```

To turn off:

```
/sbin/ifconfig eth0 down
```

cat /etc/sysconfig/network-scripts/ifcfg-eth0

/etc/host.deny
host.deny vs iptables
Completely different, since they focus on different layers. 

hosts.deny is the service layer while iptables is the routing layer. iptables will block packets of any kind. hosts.deny will depend on specific services querying it. You can run a computer without inetd but it will only prevent / allow access to services, it won’t filter pings or other concepts. Also not everything honors hosts.deny. With iptables, it has no choice. iptables is at the routing layer, before the application sees the traffic. Packets has to go through iptables before the apps even sees them.
Think of iptables as a firewall while hosts.deny as a do not allow list that some apps may follow.



## Wireless Network

| Spec | Dist | Speed | Freq |
|:----:|:----:|:-----:|:----:|
| 802.11a | 30m | 54 Mbps | 5GHz |
| 802.11b | 100m | 11 Mbps | 2.4 GHZ |
| 802.11g | 100m | 54 Mbps | 2.4 GHZ |
| 802.11n | 125m | 100 Mbps+ | 2.4/5GHz |

Going from 28 kbps dialup to easily 10 mbps cable modem. And you don't even need a telephone anymore.


