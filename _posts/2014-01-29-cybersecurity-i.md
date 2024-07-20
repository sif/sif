---
layout: post
title: "Cybersecurity I"
categories: cybersecurity
tags: cybersecurity explore
---

<img src="https://github.com/sif/sif/raw/main/files/post_files/what-gate-keeping-out-field-i-laugh-i-see-gate-wonder-why-stands-middle-nowhere-107396835.jpg" width=300px />

* TOC
{:toc}



Security trend

Security threat

https://www.wsj.com/articles/security-experts-alarmed-by-broken-cyber-market-11603359014

https://www.reddit.com/r/cybersecurity/comments/jhtiml/security_experts_alarmed_by_broken_cyber_market/

When they talk about shortage in cybersecurity talent, that's a myth

https://niccs.cisa.gov/workforce-development/cyber-career-pathways



I might merge this portion with psychology as a big part of this has to do with that

## Mentality

"How To Become A Hacker by Eric Steven Raymond"
http://www.catb.org/~esr/faqs/hacker-howto.html

"Among Cybersecurity Pros, Security Paranoia Runs Deep"
https://securityboulevard.com/2019/04/cybersecurity-pros-dont-trust-security/

If you don't trust companies, you should trust third parties even less.

It makes no sense to me why people buy, say, Google phones, then say they don’t trust Google so they install some random third party operating system.



### Motive

- Money
- Politics
- Espionage
- Personal



## Groups

Actors:

- Internal users
- Hackers (paid or not)
- Hacktivists
- Governments



Hacker organizations are either government or non-government.

Non-gov’t include Chaos Computer Club, Fancy Bear, Anonymous, etc.

https://en.wikipedia.org/wiki/The_Shadow_Brokers

Ransomware group
BlackCat/ALPHV, uses AD as gateway to compromise cloud identity providers

Clop

Storm Cloud 0539, gift card fraud, AiTM (adversary-in-the-middle) phishing pages which harvests credentials and session tokens, spear-phishing 

Narwhal Spider, phishing

Lockbit (Russian)

TA577/Hive0118 (Russian), steals NTLM to steal passwords

Fancy Bear (Russian)

## Problems and Problem Statement

“cheaper to get hacked” vs seatbelt principle (“cheap” but saves over millions)



“Bangladesh bank using $10 routers”

"An elite Wall Street bank gets a $35 million lesson: Just call tech support"
"The mistake? Tossing out old computers without wiping the hard drives."
https://www.cnn.com/2022/09/20/business/nightcap-morgan-stanley-recession-earnings/index.html



http://globalguerrillas.typepad.com/globalguerrillas/2009/12/super-empowerment-hack-a-predator-drone.html Skygrabber, $25.95



## Basics

NIST definition of cybersecurity: “The protection of information systems from unauthorized access, use, disclosure, disruption, modification, or destruction in order to provide confidentiality, integrity, and availability.”

CIA: confidentiality, integrity, availability

C: equivalent to privacy

I: modified by the appropriate party

A: ability to use when needed

Authentication (AuthN), Authorization (AuthZ)

Authentication and authorization often overlap. Availability and the other two are contextual.

An example: OS authentication (root, users, guests), which means authenticated users have certain access to resources like printers

Ex.: database authentication (database administrators)

Non-repudiation

Threat - an event, natural or man-made, able to cause negative impact to an organization 

Risk - a situation involving exposure to danger

Alerts

Available analysts

Needed knowledge

Available time

Challenges faced by security professionals
Defenders have to be right all the time, attackers just have to be right once

Amount of data created, used, etc. increased an insane amount

Consider data on server vs data in transit

Severity
Typically low, medium, high, critical



## Threat Landscape

https://www.imperva.com/cyber-threat-attack-map/
https://threatmap.checkpoint.com/
https://threatmap.fortiguard.com/

HTTPS is the gold standard for web encryption but apparently 86% of threats also hide in encrypted traffic (Zscaler ThreatLab)

2023 saw a massive growth in attacks on education (276.4%) and government (185%) (Zscaler ThreatLab)



identity threat exposure (ITE)


