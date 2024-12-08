---
layout: post
title: "Network Security Successs Guide (part B)"
categories: nyu
tags: nyu
---

<p class="blog-post-meta">(updated: February 25, 2018)</p>

<h6>Related to the class topic..</h6>
<p><strong>"What's the hardest part of the class?"</strong></p>
<p>Maybe besides the exams or quizzes? Probably the scapy assignments.</p>

<p><strong>"OSI? TCP/IP?"</strong></p>
<p>There are a few camps on this. You will hear things like "OSI is outdated" or "OSI is important, memorize it." It's hard to say what is what, with all the varying contradictions and conflicts. At least it's not as bad as the text editor war but there is some tension. I will try to keep it simple and factual.</p>
<p>OSI stands for Open Systems Interconnection. It's a model of how the internet works. There are 7 layers to the OSI.</p>
<p>(1) Physical <-> (2) Data Link <-> (3) Network <-> (4) Transport <-> (5) Session <-> (6) Presentation <-> (7) Application</p>
<p>When the data travels, it's actively being worked on. Going from the first layer to the last, the data is being decapsulated. When the data is going from last layer to first, it's being encapsulated.</p>
<p>TCP/IP stands for Transmission Control Protocol/Internet Protocol. </p>
<p>(1) Network -> (2) Internet -> (3) Transport <-> (4) Application</p>
<p>The same applies here. If you go from the first layer to the last, you are decapsulating. If you go from the last layer to the first, you are encapsulating.</p>
<p>As a textual example. You have a data that you want to send. It gets encapsulated into, say for example, UDP (UDP header and data; transport layer). Then you encapsulate it with the IP data (internet layer). Then you encapsulate it further with the frame data (frame header and footer; network layer).</p>
<p>The idea is simple. Abstract, keep it modular and make it so each layer do not have to be concern with details from other layers. If you've taken networking at NYU, you should review as much as you can as all the professors go in-depth with the foundations.</p>
<p>For example, you may not remember this and that's okay but it helps to quickly remind yourself: what is the difference between distance vector and path vector? (Answer: BGP vs RIP; Why?)</p>

<p><strong>"DHCP?"</strong></p>
<p>Dynamic Host Configuration Protocol is a layer 7 (application) protocol, it is what allows you to get on the internet. The IPv6 version is DHCPv6. Without DHCP, your computer would not be able to get an IP address. Of course, it allows you to get other data too, not just an IP address, for example, you can do a boot from a disk image over the network.</p>
<p>This is typically how it works, in short. Your computer tries to get an IP address on boot. Then your computer has to see all the addresses on the ARP table to allocate the necessary resources for it. Then it has to negotiate with the DNS servers. Only then, if all of these transactions are successful, only then will the first HTTP packet start moving.</p>
<p>Do you see the order here? DHCP -> ARP -> DNS -> HTTP (or perhaps more accurately, any others like FTP, SSH, etc.)</p>
<p>It does get more complicated, you can stick proxy and Tor in there. For fun, can you figure out what layer a proxy or Tor is in? (Answer: Application; Why?)</p>

<p><strong>"What's ARP?"</strong></p>
<p>ARP, address resolution protocol, is a layer 2 (link) protocol for IPv4. The equivalent for IPv6 is NDP (neighborhood discovery protocol). You can actually type in "man arp" and see what your doc will say. For example, typing <code>arp -a</code> will show you your current ARP table.</p>
<p>If you read <a href="https://tools.ietf.org/html/rfc826">RFC 826</a>, it will tell you the motivation behind why ARP was created. The reason it was created was because at the time, the internet was growing. As more manufacturer's made their own device, they needed a way for their device to reach other manufacturer's devices. Either they could make their own which introduces a whole set of problems, each individualized to the manufacturer's or they could just create one standard for all.</p>

<p><strong>"DHCP Starvation?"</strong></p>
<p>DHCP starvation is a form of denial of service attack and it means what you think it might mean. It's easier to do the lab if you understand what exactly is "it." If you have a target where you don't want them to serve a range of IPs. Say a DHCP server. If a DHCP server cannot issue IPs to prospective clients, then the client that utilizes this DHCP cannot do anything, like go to the beloved YouTube. It can only communicate with itself. (What is this address?) This is why it's called a denial of service.</p>
<p>With that in mind, if you have a target, you just need to think about how to starve it. Another way to think about the lab assignment is looking at the other side of the door. How would you prevent it? One way is to limit the MAC address it (why?). In vendor-specific terminology, you'd use "Port Security," which means that that port is only allowed a certain number of MAC addresses. Once that limit is reached, the attack would stop. Would this work if this attack is a distributed one? Would iptables work? What will you do if you're hit with Gobbler or Yersinia (one MAC address per IP request)?</p>
<p>So, now that you know that, going back to the other side of the door (and assuming you know this feature isn't used), how would you write Python to attack this server?</p>
<p>On a side note, can you think of a way to map out your target?</p>

<p><strong>"ARP Poisoning? ARP Spoofing?"</strong></p>
<p>When a machine needs to figure out its network, it uses the table. So, if it wants to get something like an IP or see who is the gateway, it uses the table. It's stateless and resolves between IP and MAC. You just need to type "arp -a" and you can see the relevant information. You can also modify the table from command but the assignment requires that you use Python (and scapy).</p>
<p>The idea is to set it up in such a way that the attacker (you, for this assignment) can listen in on all connections being passed between the router / switch and the victim / target. To defend against ARP spoofing, web servers should provide SSL. You will see SSL but your job is to exploit the weakness and strip it.</p>

<p><strong>"TLS? SSL?"</strong></p>
<p>You will need to understand this for one of the lab. TLS is Transport Layer Security and SSL is Secure Sockets Layer. They are both the same class of product. The intended purpose is to try to encrypt the data being communicated between the users and the website. SSL is the predecessor of TLS. You can look at your certificate anytime you see the S in HTTPS. What is the certificate authority in TLS/SSL? (short answer, they issue certificates; how?) Is the encryption assymetric or symmetric? (short answer, symmetric)</p>

<p><strong>"MitM?"</strong></p>
<p>MitM is Man in the Middle. Or rather, man in the middle attack. It is what it sounds like. The attacker insert themselves between two points. Suppose two points, A (user) and B (server). The attacker insert themselves by creating two extra connections.</p>
<p>From A's perspective, it looks like they're connected to the server. From the server's perspective, it looks like they're communicating with the right user.</p>
<p>So, a real world example, if somehow the attacker has the private key, they can effectively monitor <strong>all</strong> communications without either party ever knowing.</p>
<p>Another example is when they don't have the private key but can listen in on your connection. There was one method that used to work. What happened was that the attacker would copy-while-forwarding every data then during their leisure time, attempt to break it.</p>
<p>The way to mitigate this was either make the key "unbreakable" (can you tell me how?) or utilize PFS (perfect forward secrecy).</p>
<p>Of course, PFS isn't perfect. All it means is that if somehow, the attacker were to figure out the key in the future, they cannot use the key they discovered in the future to break open your system in the past. The key would only be useful for the attack at that time.</p>

<p><strong>"127.0.0.1 vs 0.0.0.0?"</strong></p>
<p>When you write a client/server (or just working on the lab) and need to bind, you'll run into the issue of trying to figure out what to bind to. 127.0.0.1 is when you want to listen to the loopback interface (lo0). 0.0.0.0 is when you want to listen to all interfaces. Another fact, you can't bind to ports lower than 1024 without the proper privilege. This is discussed <a href="https://www.w3.org/Daemon/User/Installation/PrivilegedPorts.html">here</a>. The reason is simple: "This is a security feaure, in that if you connect to a service on one of these ports you can be fairly sure that you have the real thing, and not a fake which some hacker has put up for you."</p>

<p><strong>"Subnet mask?"</strong></p>
<p>Quick note, a year or so before the time of this writing, BGP / RIP material wasn't covered in-depth on the CCNA curriculum so it's probably okay not to know this all the day. The same goes with subnet networking.</p>
<p>"4.6 Configure and verify single-homed branch connectivity using eBGP IPv4 (limited to peering and route advertisement using Network command only)"</p>
<p>As of this writing, there are apparently more material on subnet and a push for more BGP / RIP testing.</p>
<p>A subnet mask is two parts. It's an IP address that's extended and the host address. There are 32 bits in the address and it is the result of the bitwise AND operator on the netmask. As a matter of fact, read everything <a href="https://www.computerhope.com/jargon/n/netmask.htm">here</a>. It is worth delving into routing protocol and subnetting for certification purposes.</p>

<p><strong>"RIP? BGP?"</strong></p>
<p>Routing Information Protocol and Border Gateway Protocol is used by routers to send data from one place to another. RIP is a distance-vector protocol as opposed to BGP which is a path-vector protocol. One way to think of it is, RIP will tell you how far it takes to get from A to B. BGP will tell you if there is a path from A to B.</p>

<p><strong>"DNS?"</strong></p>
<p>This one can cause confusion (at least for me, initially). The easiest way to think of this topic is this, DNS is a software you install on a web server. Any server that has DNS installed and setup is called a name server. The follow up question is, what is a name server (or nameserver)? A name server is the same thing as a DNS server. An example of use is to map an address to an alias.</p>
<p>Regarding how to setup a nameserver, you'll need a VPS or a dedicated hosting plan (obviously, a shared hosting plan won't work).</p>
