---
layout: post
title: "Site Reliability Engineering"
categories: reliability_engineering
tags: reliability_engineering SRE down_detector SNOW
---

* TOC
{:toc}

Error budget = 1 - SLO

so if SLO is 99.9%, then 1 - 99.9% gives us 0.1% error budget

"In a nutshell, DevOps Engineers are ops-focused engineers who solve development pipeline problems. Site Reliability Engineers are development-focused engineers who solve operational/scale/reliability problems."

They are not mutually exclusive

DevOps starts with development, automating and optimizing the steps to production

SREs focuses on production, reaching back into the pipeline to improve it



rolling restart is when a group of processes running in a cluster is restarted while maintaining high availability



Availability != Uptime



Measuring availability:

Time based availability = uptime / (uptime + downtime)

Aggregate based availability = successful requests / (successful requests + failed requests)



MTTD mean time to detect

MTTF mean time to failure

MTTR mean time to resolve

MTBF mean time between failures



Observability



Probes

Readiness probe

Liveness probe

Startup probe



Pod logs



## Production Support

we engage in production monitoring/alerting and building observability

application support is also production support (for us at least)



be mindful of OKRs

Do be careful, we do not want to own everything



Find session from customer during triaging

know the products

see inconsistencies



### ServiceNow



### Netcool

"IBM Netcool is a suite of software products that provides a range of solutions for managing and monitoring IT infrastructure, including network devices, servers, and applications. The Netcool suite includes a range of tools and applications for managing and monitoring IT infrastructure, including:

- Netcool/OMNIbus: A real-time event management and correlation platform for IT and network operations centers.
- Netcool/Impact: A policy-based event processing and automation platform for automating and managing complex IT environments.
- Netcool/Proviso: A network and service provisioning platform for automating the provisioning and configuration of network devices and services.

Netcool is often used by large organizations to manage and monitor their IT infrastructure, as it provides a range of tools and capabilities for handling complex environments and automating many common tasks."



### Downdetector



### Dark Canary

Feature flag

Flag monitoring



### Control-M

Control-M is good for scheduling batch jobs

"Planning involves setting up the jobs to be executed and defining their dependencies, scheduling criteria, and other parameters that are required for their successful execution. In other words, planning involves creating the job definitions and specifying how and when they should be executed.

Monitoring, on the other hand, involves observing the execution of the jobs in real-time and making sure that they are progressing as expected. Monitoring includes tracking the job status, identifying any issues that arise during the job execution, and taking corrective action if necessary."

Planning



Monitoring



## Runbook



## Incident Management Process



Priorities (1 is highest)
P1
P2
P3



"An incident is any event which is not part of the standard operation of a service and which causes, or may cause an interruption to, or a reduction in the quality of that service."

Typical activities:

- recording activities to approved Enterprise Incident Management System of Record (SoR)
- providing status update to the impacted customer/client and management
- monitoring incidents through resolution

Five stages:

1. Identify, Log, Evaluate, Submit
2. Own, Monitor & Track
3. Diagnose, Mitigate & Document
4. Resolve & Close
5. Evaluate and Manage Process Performance

Incident Classification



## Problem Management Process

"Problem Management process is to improve IT service delivery through proactive and reactive identification and removal of errors within the applications and services."



## Change and Release Management Process

Change Incident (CI)

Release Attestation



Risk Rating can be increased, not lowered



Emergency change request (ECR)



## Scenarios

One of my favorite because I've experienced a lot of these in some way:

https://twitter.com/MosquitoCapital/status/1593541187675516928

"1) Random hard drive fills up. You have no idea how common it is for a single hosed box to cause cascading failures across systems, even well-engineered fault-tolerant ones with active maintenance. Where's the box? What's filling it up? Who will figure that out?

2) Physical issue with the network takes down a DC. I gather Twitter is primarily on-prem, and I've seen what happens when a tree knocks out a critical fiber line during a big news event.

3) Bad code push takes the site down. Preventing this was my day job, and I can tell you that it's one of the scariest scenarios for any SRE team, much less a completely understaffed and burnt-out one.

4) Bad code push takes the site down *in a way that also fucks up the ability to push new code*. This is the absolute nightmare scenario for teams like mine. When something like this happens, it's all hands on deck. Without deep systems understanding, you might never get it back.

5) Mystery SEV. Suddenly, the site goes dark. The dashboard is red. Everything seems fucked. There's no indication why. You need to call in the big guns. Teams with names that end in Foundation. Who are they? How do you call them?

6) Database is fucked. It's a big one. Everything is on fire. Who's the expert for this one?

7) Someone, say, entirely hypothetically, @wongmjane, finds a critical security vulnerability in your prod iOS app. You need to fast-track a fix, *stat*. You have a team of experts who know how to navigate Apple's Kafkaesque bureaucracy for app updates, right? I sure hope you do.

8) Someone notices that it's possible to read anyone else's DMs by loading up a particular URL. This is a SEV1, massive, all-hands-on-deck, critical issue. You need people who understand deeply how your privacy abstractions work, and how to fix them.

9) The site goes dark at 4am. The oncalls have no idea what's wrong. You *need* an IMOC (Incident Manager On Call) who knows who to wake up, why, and how. Someone who understands your systems, can synthesize information at lightning speed, and coordinate a recovery effort.

10) The system you use to *find other systems* internally goes down. None of your systems can talk to each other. The site, and all your tools, immediately fail. The tools you need to revert the breaking change are all FUCKED. Can you figure this one out with a skeleton team?

11) It's 5pm on a Friday. The dashboards all go red at once. The web fleet is seeing cascading reboots. The disks have been filling up since Wednesday. There were hundreds of code changes across multiple interlocking systems on Wednesday. Revert any of them at your own risk...

12) Oh shit. You reverted one of them. Now every locked account's tweets are visible to everyone. People might literally get murdered with machetes over their posts. That's not a hypothetical. It's now 9pm. The site is fucked. Who are you going to call?

13) The system that ensures server changes are safe to push to prod is failing. You have, say, 30000 tests that *must* run to ensure privacy/security/compliance/reliability. One of the tests is causing the failures. Can you find it? Also it's the World Cup. Also the site is down.

14) A user in the Phillipines is about to post CEI to the platform. You *cannot* leave that content up. Do you have your employees with relationships with PH law enforcement? Do you have your content moderation systems working? Do you have your moderators?

15) The FBI wants to inspect the contents of the DMs of someone they think is about to commit 9/11 2: Atomic Boogaloo. Do you have a system to grant them access? Do you refuse them access? How do you know it's really them?

16) You grant them access. Now someone from a country known for horrific human rights violations is knocking. They have an official-looking subpoena. Do you let them see a dissident's DMs? Can you articulate why? You might need to, in a very official court somewhere in Europe.

17) Another country is telling you that they want all of your data on their users stored on servers in their country. Do you have policy experts for that country? Do you have a lot of *very* motivated lawyers? Do you have an infra eng who knows how to partition your data just so?

18) GDPR. You're found in violation. It took a team of 100s of engineers, lawyers, policy experts, designers, and managers months of "hardcore engineering" to be in compliance in the first place. Can you get back? I assure you, not doing so will cost more than an org's headcount.

19) Once a day, every day, at 12:13am, a specific service in your data pipeline slows to an absolute crawl. It doesn't seem to be causing any issues, but you're a bit concerned as it seems to be getting worse. Do you assign an SRE to take a look? Do you have any left?

20) The service you use to discover other services is working fine, but one of your best engineers does some calculations and realizes it won't scale to more users and more services, and (hypothetically) you want to build a super-app called X. Do you rewrite? What do?

21) You decide to rewrite. 8 months later (lol) your new system is ready to take on its first users. Who's coordinating the migration? Do they *really* understand complex systems? Are they good with people? Can they execute? Do they have the domain knowledge they need?

22) You just hired a great-seeming engineering director from Microsoft for a core org. Slowly, their org's productivity slows, and attrition climbs *way* up. The director swears everything is fine. If you fire the director, one of your VPs suddenly has like 18 reports. What do?

23) An engineer just kicked off a command to reboot the fleet. Oops, they didn't use --slow. Now all of your caches are empty. All of them. Every request goes straight to DB. The DBs all get overloaded instantly, some start to OOM and reboot loop... How do you refill the cache?

24) World Cup. It is *the* defining event. We used to have watch parties for the traffic charts. The amount of traffic your site gets in one week is mind-blowing. It's in huge bursts. It tests *every* system you have to its limits. If one breaks, hope it doesn't cascade. It will.

25) New Year's Eve, USA East Coast. Every year. I remember sitting outside the office, fireworks exploding in the distance, frantically calling the video oncall. Everyone posts videos of their fireworks. *Everyone*. It will fill up disks and test your bandwidth to the very limit.

26) I've said it before, but... CEI. If you mishandle it, if your policy people and lawyers are not top of the fucking line, you *will* get yanked in front of Congress, in front of judges, into the evening news, places you don't want to be if you're running a social media company

27) Physical security of your offices. Security guards told me they keep *long* lists of crazies, commit them to memory. People want to fucking kill Zuck. Like ritual murder in the bathtub shit. They show up at the office *all the time*. Is your security team staffed and ready?

28) Genocide. People use your platform to orchestrate mass murder, the machetes in churches kind. And fast. Lightning fucking fast. You need to be prepared *before*. If you don't have a team who knows how to detect and stop this ASAP, your ass is getting dragged to The Hague

29) Rebellion. Millions of people will use your platform to orchestrate rebellion against their government. Do you use the tools for #28 to stop them? Do you let it ride? How do you decide? What if you let it ride and the same thing happens next week in a country you really like?

30) Bus Factor. Say you have 3 senior+ level SREs left in your Core Services org. They are absolutely indispensible, for reasons you can infer from above. How do you keep them all alive? Can they be on the same plane? What's the contingency plan if they all kick it anyway?

31) Invaders. A single box in your datacenter is mistakenly connected to the public Internet and forgotten for years (this really, really, really does happen, I promise). Someone pops the box. They're in. How do you detect it? What do you do once you do?

32) Invaders: The Quiet Ones. They're in your network. They're just watching, and waiting. Not doing anything. I promise you, a great security org can detect even this. If you don't have a great one left... What damage can be done by observation? Credit card data? Passwords? DMs?

33) Invaders: State Actors. The CCP just gained access. If they have their way, they're here to fucking *stay*. How will your security team find out? How will they find and eradicate backdoors? How will you protect user's DMs and private tweets? If you don't, people will die.

34) Invaders: The Chaotic Ones. They're here to do some fucking damage. They could delete data, reboot the cache fleet and take down the site for weeks, post nuclear threats as the POTUS... You better have a big, talented, experienced security team if you want to be ready.

35) On the subject of Invaders... How's your corporate IT security? It's easy to just think about the production fleet, but what if an eng's laptop is stolen from their Camry? Can you detect that before it's reported? Can you remotely lock & wipe? Invalidate their keys?

36) And again, how's that physical security team? Someone will absolutely try to plug a Raspberry Pi into your corp network. 100%. They'll try to spoof the wifi. Mics in the executive offices. 1960s spy movie shit. I'm not joking.

37) Content moderation. You need 3 things: a *giant* team of people checking reports 24/7, another team working on tooling to help that team, and regular psychiatry appointments for the first team. Not kidding, again. Humanity is DARK. Your moderators can and will commit suicide.

38) Oops! You didn't hire a content moderation team. Your site is full of very nasty stuff. Everyone leaves because it's so unpleasant, or (worse for you personally) you get dragged into court for breaking all kinds of decency, piracy, and privacy/harassment laws.

39) Oops! You didn't hire a team to build tooling for your content moderators. They are completely overwhelmed by the literally millions of reports. They burn out, you can't replace them fast enough, and #38 happens anyway

40) Oops! You didn't pay up for psych appointments for your moderators. Best case, they leave as husks of their former selves. Worst case, suicide. You're in the news/courtroom. (Ok, or worst-er case, one of them shows up to work with a gun. How's that physical security again?)

41) Speed: Backend requests. Some network change bumps the RX rate. Suddenly it takes a couple dozen milliseconds longer to load the feed. Ever seen the statistics for what happens to retention rate? It's mind-boggling. Now imagine it getting slightly worse, every day

42) Speed: Scrolling. You wouldn't believe how many tens of thousands of people will stop using your app, forever, if some Android change adds the slightest lag to scroll times. Do you have client perf experts left? What if the problem keeps getting worse? How do you debug it?

43) Speed: Cold start. If you add 5 seconds to the time it takes to start your app from nothing, you will TANK your onboarding rate. To an unbelievable degree. I mean, push it into the fucking ground. They'll never try the app, ever. Have perf experts on all client platforms?

44) Speed: Hot start. Some Android change makes it where loading the app takes 1 second longer. Suddenly, 25,000 fewer people are using your app every day. Those numbers will start to grow. I know it seems ridiculous, but this shit is REAL. How do you track start times? Do you?

(I know that some of these don't seem like immediate existential threats to the product, but trust me - to varying degrees, *any* one of these problems can be the difference between the app succeeding or failing. What might seem like an insignificant problem can snowball. Fast.)

(And the sweet Lord help you if you have to deal with more than one of these problems at a time. And LORD help you if it's while staffing a global communications utility with a skeleton crew after a giant loss of technical tribal knowledge.)

45) DATA LOSS. Holy shit, data loss. Do the people who understand your backups still work there? Hot backups? Cold backups? Data redundancy between regions? If you lose user data, it's game over. Trust is gone, permanently. Fire, nukes, floods, humidity, errors, drive defects...

46) Data loss again. Do you have read-only backups? A bad actor could absolutely try to wipe all your disks. Can they damage your tape drives from software? How long will it take to restore the entire site if everything gets wiped? (Hint: Probably weeks. Best case.)

47) Deletion. You need to know, for sure, that data is deleted from the site. This is far more important than you think. If a post is deleted, is it wiped from cache? What happens to that post in read-only cold storage? If you fuck this up, you're 100% gonna end up in court.

48) Employee burnout. I know this seems silly in a vacuum, but trust me, this shit is real. Look up the HBR series on it. You will lose critical employees. People you can't just buy back. No amount of money. People you can't afford to lose. Not lazy people. Good ones. Great ones.

49) Governmental interference. What if Brazil decides to cut you off? The US? Saudi Arabia? Do you have policy people, lawyers, lobbyists, ex-diplomats? Who will you appease? What about countries with conflicting interests? Say you can't make them all happy. Who do you choose?

50) Replication. Fuck. Um. You have, say... 5 primary regions. Each region has a copy of all mission-critical data. One day, some eng realizes that some data in A is different in B. This is *apocalyptically* bad. Which region is correct? How do you decide? How do you fix it?

51) Employee account privileges / service accounts. Can every employee reboot every server in prod? Should a help desk employee be able to see credit card details? How do you give access to only certain commands or boxes? Automated users? Can someone hijack an automated user?

52) DNS! If you fuck up DNS settings somehow, your entire *everything* can go dark. And I mean everything. Internal tools, the entire website, the literal DOORS TO YOUR OFFICE (that's not hypothetical). And if your DNS registration lapses, someone can steal your site! Forever!

53) Certificates. The magical lil "s" in "https" that keeps Bobby Joe at Peets from stealing your credit card details. If your website cert registration lapses, you would not BELIEVE the pain you're in for. Spoofing, services breaking, people completely unable to load the site...

54) Tests! Nope, no joke. If someone isn't keeping a close eye on your unit and integration and e2e and canary test suite, you can: Break every build and never ship. Push horrible, possibly illegal, bugs to the site. The worst is if all the tests *silently, incorrectly, pass*...

55) Payments. There are SO many laws, regulations, and policies around payments that you *absolutely must* be in compliance with. Any slip-up can get your ass yanked from the banking system. No, doggie coins won't cut it. Ads, verification, whatever - your revenue is fucking GONE

56) Spam! Spam is an *existential* threat. You need automated systems, AI-based clustering, entire teams doing manual review, and some *extremely* smart, driven, and creative engineers adept in adversarial thinking because you absolutely must be one step ahead at all times"
