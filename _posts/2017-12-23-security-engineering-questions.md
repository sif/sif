---
layout: post
title: "Security Engineering Questions"
categories: questions
tags: questions security_engineering cybersecurity_engineering packet_analyzer
---

## Intro

This is my <em>personal</em> preparation notes for security engineering roles. In addition to <strong>my course studies</strong>, I get these questions from variety of sources around the internet. I try to answer in my own words.
If you are preparing for the same role, just remember - <strong>don't memorize</strong>. That's how I'm approaching it. If I'm completely lost on a question, I won't even bother putting it down here.
I admit, it's tough for sure, like drinking from a fire hydrant; c'est la vie.
Disclaimer to employers, I will not reveal any actual interview questions. Any interview questions here are ones I found on the internet (such as on glassdoor).

## Lab Setup

<ol>
<li>Burp Suite</li>
<li>Nmap</li>
<li>Wireshark</li>
</ol>
(Or just setup and use Kali on a VM.)
On a side note, if you think you found a bogus phishing email, forward them to: spam@uce.gov, reportphishing@antiphishing.org

Step by step

<ol>
<li>Recon</li>
<li>Scanning</li>
<li>Network</li>
<li>Password</li>
<li>Reporting</li>
</ol>

## Questions (and Answers)

<ol>
<li>"What is \r?" Carriage return. It'll move the cursor back to position 0. Different from \n which will return cursor back to position 0 on the next line. Apparently useful for older devices. This is <a href="https://www.youtube.com/watch?v=fpRZsVrVrkU">ridiculous</a>. Useful but ridiculous. Imagine a 10 minute lesson on \n...</li>
<li>"Describe in detail how traceroute works." This command does what it sounds like, it traces routes. It tells you the time it takes to get from one hop (or node) to the next. It tells you about the device (like identity and latency) that it hops to.</li>
<li>"How would you go about securing a web server<a href="https://www.glassdoor.com/Interview/Google-Security-Engineer-Interview-Questions-EI_IE9079.0,6_KO7,24.htm">?</a>" This is an "in general" answer. Remove unnecessary services. Remove unused applications. Close off remote access. Separate environments, for example, production, testing and development. Watch for who has what permissions and privileges. Regularly install stable patches and security patches. Audit often. Regularly red team and blue team the web server. Continue to be educated (personally or team).</li>
<li>"Write a function to determine if an input is a power of 2." Look at the binary of the powers of 2. For example, 00000000 is 0, 00000001 is 1, 00000010 is 2, 000000100 is 4, etc. Then build cases. For example, if the input number is an odd number or not a number, return an error. No need to check. Write a function or use something built-in that converts the input number to binary. Then compare. <strong>An alternative</strong> is to keep dividing by 2 until it gets to 1. This is probably better as it's easier. The idea is the same with figuring out if there is a negative involved. You just keep multiplying. As usual, if it's an odd number, don't even bother.</strong></li>
<li>"Describe a TCP handshake." This is what a typical handshake session look like:
<br />Client --SYN--> Server
<br />Client <--ACK/SYN-- Server
<br />Client --ACK--> Server
<br />The question that usually follows is, "why?" The answer is because we want to ensure that the packets are actually delivered. To avoid the handshakes, just use UDP. So, the transactions require some explanation. First the client sends a SYN and gives a sequence number to the server. The server ACK (acknowledges) the sequence number and then does the same, generate and sends a sequence number to the client. The client then acknowledges and sends the ACK packet to the server.</li>
<li>"What is buffer overflow?" A buffer overflow is a class of attack where the program goes out of bound of what's allocated for the memory space. Typically this'll crash the program.</li>
<li>"What are common web vulnerabilities." SQL injection, XSS, poor (or no) security configuration, social engineering (not sure if count but viable attack surface), unvalidated redirects, unvalidated forwards.</li>
<li>"What is the opposite function of malloc() in C<a href="http://www.gwan.com/blog/20160405.html">?</a>" free()</li>
<li>"What Unix function lets a socket receive connections?" listen()</li>
<li>"How many bytes are necessary to store a MAC address?" 6 in binary; 12 in hexadecimal (17 with delimiters)</li>
<li>"Sort the time taken by: CPU register read, disk seek, context switch, system memory read." CPU register read, system memory read, context switch, disk seek. From fastest to slowest. Hint, context switch is a problem for microkernels.</li>
<li>"What is a Linux inode?" I actually agree with the answer that it's a "a unique file identifier for any given file system." Not sure why the insistence on metadata. From <a href="https://www.slashroot.in/inode-and-its-structure-linux">here</a>, it suggests that it's interchangeable. So, you can also say that "an inode is metadata of the data." I worry that answering this based on the first thing that comes up to my mind will penalize me.</li>
<li>"What Linux function takes a path and returns an inode?" stat(), fstat(), lstat(), fstatat(); stat for status, fstat for file descriptor status, lstat for symbolic link status, fstatat for status relative to a directory file descriptor</li>
<li>"What is the name of the KILL signal?" Terminate? I would've gone for SIGKILL and the signal code if I remember that as well (9). Also not sure why the answer is wrong.</li>
<li>"Why Quicksort is the best sorting method?" It's not. It has a O(n^2). In practice, I agree that: ""big-O" ignores data storage latencies, topology, volume, available memory, and even the computational cost of every CPU instructions involved in a given implementation – instead, it merely counts the number of algorithmic operations! Big-O can be a valuable indication when designing algorithms but the best performing and scaling solution depends on the particular constraints of any specific problem and environment."</li>
<li>"There's an array of 10,000 16-bit values, how do you count the bits most efficiently?" Then ... I think they wanted a hash table? I suppose the correct answer is a hash table. Not sure what's wrong with that person's answer though. I can't deny that you can use hash table for just about everything including this problem.</li>
<li>"What is the type of the packets exchanged to establish a TCP connection?" SYN, SYN-ACK and ACK (synchronize and acknowledge)</li>
<li>"Explain CSRF." CSRF is short for cross site request forgery. The best way to think of it is as "session riding." The attacker takes advantage of the authenticated user.</li>
<li>"Explain same origin policy." It's a policy that dictates that the site and the following site come from the same origin. It's dictated by URI scheme, host name and port number. It tries to prevent the attacker from taking advantage of that site's DOM (Document Object Model). As an example, http://siferaseph.com is different from https://www.siferaseph.com.</li>
</ol>

## Hack Night at NYU

<ol>
<li>On a Linux VM:

1. apt-get install gcc-multilib
2. apt-get tmux
3. wget https://raw.githubusercontent.com/blankwall/Template/master/socat.sh
4. git clone https://github.com/wi-fi-analyzer/fluxion</li>
<li>Day 1:

1. ./load-tmux-profile.rb exploit ../Binary_Exploitation/exploit_1/exploit_1</li>
<li>Day 2:

1. Microsoft Word
2. https://github.com/n1nj4sec/pupy

otw up-to: koReBOKuIDDepwhWk7jZC0RTdopnAYKh (level 5)</li>
</ol>

## Assembly Notes

<table class="table table-bordered">
<thead>
<tr>
<th scope="col">Code</th>
<th scope="col">Description</th>
<th scope="col">Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>mov src, dest</td>
</tr>
<tr>
<td>add src, dest</td>
</tr>
<tr>
<td>sub src, dest</td>
</tr>
</tbody>
</table>

## IRC

If you are like me and still use IRC... then you're probably going to want to setup Tor.
<ol>
<li>Put said onion into network list. (SASL EXTERNAL)</li>
<li>openssl req -x509 -new -newkey rsa:4096 -sha256 -days 1000 -nodes -out network-name.pem -keyout network-name.pem</li>
<li>Make sure said app can use this cert.</li>
<li>openssl x509 -in network-name.pem -outform der | sha1sum -b | cut -d' ' -f1</li>
<li>Add this fingerprint to the list (unfortunately, on plain internet first).</li>
<li>Make sure SSL is enabled (invalid if necessary, since some CA won't issue onion certs).</li>
<li>Connect and enjoy.</li>
</ol>

## Phreaking

Haven't touched this for years but if you're one of the relatively few who enjoy this topic:
<ul>
<li>Google -> "Recently used devices"</li>
<li>##72786# = delete phone info from settings</li>
<li>Blue is iPhone; Green is Android (this is a thing people fight about)</li>
<li>To get a different tower.. turn on and off Airplane Mode.</li>
</ul>

Regarding stickers (a fight I actually got into), don't put them on your laptop. Maybe over the webcam if it doesn't come with some kind of guard. I don't know why people put it on their laptop shell but it's often ugly. As much as possible, use the device as intended.
