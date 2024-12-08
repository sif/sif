---
layout: post
title: "0x00sec CTF Exercise #1 Remediation"
categories: ctf
tags: ctf
---

<a href="https://twitter.com/pry0cc">@pry0cc</a> asked in Discord if anybody wanted write up something about remediation. I volunteered with <a href="https://twitter.com/Cryoplex">@Cryoplex</a>. The last time I did a CTF was in college so I'm rusty.

## The Attack

Anyway, let's get straight to it. You can find the exercise here. As noted, there are multiple ways to solve this. The first exercise is about web security. It looks like this.

<img src="https://miro.medium.com/v2/resize:fit:1118/format:webp/1*eYT0vLFUsmRMyadtG_gN0Q.png">
0x00sec Exercise #1

In order to recommend any remediation, you should know how the attack is carried out. So, just looking at this, we need two piece of information.

Cryoplex found that the server was running Nginx 1.17.5 and PHP 7.3.14 according to Wappalyzer. It's on a Digital Ocean server with 80 and 443 open according to Shodan.

Useful information, since this means that we'll probably deal with files in PHP. The frontend is finished in Bootstrap. Nothing to it so far.

<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*OW4WKZ368jaE5rysnv6Rig.png">
Bootstrap

When you scroll down for something new, you will see this little snippet.

<img src="https://miro.medium.com/v2/resize:fit:1400/format:webp/1*iaEKVqKZTZswZBnWxsRdyQ.png">
A hint!

This is a little hint on where to look. Even if this hint wasn't there, you likely would've found this by trial and error.

The hint tells other developers to delete the git directory after publishing. Thus the username and password is probably in there.

First you'll need to install something that will rip the git repository. Fortunately, somebody have already written a tool to do just that. You can get <a href="https://github.com/kost/dvcs-ripper">dvcs-ripper</a> here.

First, run this:

<code>git clone https://github.com/kost/dvcs-ripper.git
cd dvcs-ripper/</code>

Once you are in the new directory, do this:

<code>./rip-git.pl -v -u https://exercise-1.0x00sec.dev/.git</code>

We know it's .git because of the hint. It was the first thing to try and it worked. After the script runs, you'll see new files. The one you need is in index.php.

The code in index.php has the username and password. Great! It even tells you that it's a SHA256 hash.

The next thing to do is to try to break the SHA256. Now, because hash functions like SHA256 are one way, it's easier to use something like a dictionary attack.

Cryoplex found the <a href="https://github.com/praetorian-code/Hob0Rules">combination that worked</a>. First, install hashcat if you haven't. I kept my install simple and went with this doc.

<code>git clone https://github.com/hashcat/hashcat.git</code>
 
Change your directory to the new location.

<code>make && make install</code>

Look for the hash mode for hashcat <a href="https://hashcat.net/wiki/doku.php?id=example_hashes">here</a>. We need SHA256, this is: 1400

Download Hob0Rules and change your directory to there. We'll want to use rockyou.txt so run this:

<code>gunzip rockyou.txt.gz</code>

Remember that SHA256 password? Put that into a text file on your desktop or something and call it "hash.txt."

Finally, run this:

<code>hashcat -a 0 -m 1400 ~/Desktop/hash.txt ~/Downloads/Hob0Rules-master/wordlists/rockyou.txt -r ~/Downloads/Hob0Rules-master/hob064.rule -o ~/Desktop/cracked.txt</code>

Here's the rationale.

I used 0 for -a because I wanted to start with something straighforward for attack mode. We've already covered which hash mode we want to use.

I left my hash.txt file on the Desktop and Hob0Rules in my Downloads folder. The second directory tells hashcat what set of words to use and -r tells hashcat what ruleset to use.

If successful, your password should output to cracked.txt.

## Remediation

Now that you see how the login is obtained, we want to make sure this doesn't happen to our client. What can we do?

There are two scenarios here. The first is that the client has already published their password. Then the first thing you'll want to recommend is that they change the password first thing first.

There is a tool called <a href="https://rtyley.github.io/bfg-repo-cleaner/">BFG Repo-Cleaner</a> which will allow you to clean out your history. It was made with this scenario in mind.

A full <a href="https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository">guide</a> is here.

The second scenario is best practice, where the client might be making their first push. If this is the case, one thing a client can do is to put their credentials into a configuration file. Then there should be a way so that the configuration file is never pushed to the repository.

I hope this was easy to follow along! Thank you for reading.

Originally published at: [0x00sec CTF Exercise #1 Remediation](https://medium.com/@cassandriel/0x00sec-ctf-exercise-1-remediation-30a9cd74c950)
