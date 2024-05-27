---
layout: post
title: "You Need a Runbook!"
categories: sre
tags: runbook sre documentations
---

(Originally published at: <a href="https://www.nyedis.com/post/you-need-a-runbook">You Need a Runbook!</a>)

In the tech industry, programmers have a reputation for not wanting to write documentations. The running joke is that you’ll have job stability if nobody understands your work. The truth is, writing is hard. Having to understand the deep technical work of your project and turning that into something that everyone else can understand is not easy. You have to know your audience and write just enough that it makes sense for the project. In other words, if it’ll be referenced by only 3 people, you’re probably not going to be motivated to write a 1,000 page tome. This problem carries over to other parts of the tech world.

As a SRE, I often have to work with developers. If their documentation is sparse (and most of the time, it is), I need to chase them down and work with them to develop a runbook that the rest of the organizationcan can use. Many developers like to think of their code as their baby and can become defensive if you start asking questions. Knowing how to defuse their ego will be important as you’ll need to maintain a regular channel with them to build reliable systems. They’ll often refuse at first, telling you that their stuff works just fine and will never break. It works until it doesn’t. If it breaks and they’re unavailable, who else can get it back up and running again?

I have lost count of how many times we have run into an issue and the core developer is nowhere to be found. Forget the original developers, we often cannot even find their backup. This occurs for many reasons. These include that they’re either away on vacation, the other members aren’t as familiar with their work, or they are swamped with other active issues that takes priorit. To solve this, we often have to escalate, and if they were sleeping…nobody is happy.

This is where a “runbook” comes in. This documentation is one of the most important and effective tools in a SRE’s arsenal. You could literally have a team dedicated to the upkeep of the runbook archive as we do in our organization. It is so important you should never proceed with a project (in the context as a SRE) unless you have access to the application’s runbook (or are able to develop one). You could also get the developer’s personal phone number and call them at 3 AM. Without either, the first finger that will be pointed at is...you, when the blame game starts. The runbook simplifies things. In the real world, you can’t just shut down an application. You’ll have customers, live issues, etc. There are a lot of moving parts. Unless you are only going to support one application for the rest of your life, you can’t possibly remember every little nuance. You’ll likely be supporting many applications and the systems are likely very complex as the organization grows. The runbook serves as source of truth for both you and the developer. For the developer, this will ensure that they did their part in imparting the knowledge needed to run the application. This means exposure of source code to the appropriate individuals, code review by unbiased partner teams, etc.

For the SRE, we have an authoritative source of truth. If you don’t trust me, you can trust the developers who signed off on this. If the developer says that a flag needs to be activated before you can restart a Java applet, you should probably follow that advice. Not doing so will make it worse and risk more problems. It’s like listening to your doctor. Unless you have a good reason not to trust your doctor, you should at least get a second opinion. A complete mistrust of the entire medical industry is a very bad idea. It is the same with this – complete mistrust of both the entire SRE and AD(Application Development) team is a recipe for disaster. The point is, there should be a minimal level of trust in order to operate. On that note, the ability to continue operation implicitly provides reliability. You can ensure that if something goes down, you can take the necessary steps needed in the runbook to keep the system going.

A runbook also serves as a measuring stick. You can often tell how well teams work with each other based on the quality of the runbook. If I can grab a random stranger (with some tech knowledge and experience) off the street and give them a summary explanation and a runbook and they can get started, that is a very good runbook. This means that different teams got together and were able to produce a document that an audience with different levels of knowledge and ability could follow. If the developers, SRE, etc. were all on vacation and only the CEO is there, can the CEO follow the runbook? (The answer should be yes.) The runbook should make everyone’s life easier, not harder. How do you provide reliability? When everybody knows how to keep the business going.



Sifer Aseph

Cybersecurity Engineer @ Nyedis
