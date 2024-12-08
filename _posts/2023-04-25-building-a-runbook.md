---
layout: post
title: "Building a Runbook"
categories: sre
tags: runbook sre documentations
---

(Originally published at: <a href="https://www.nyedis.com/post/building-a-runbook">Building a Runbook</a>)

<a href="https://www.nyedis.com/post/you-need-a-runbook">Editor's Note: In Sifer's recent piece which you can click on here he discussed why you need a runbook. In this blog, he gets more into detail with what you need to include in that runbook.</a>

If I could snap my fingers and change one thing about my work at the bank, it would be to make sure that everybody documents their work more. It's not that they're not documenting, they do, but often just the bare minimum. I would bet that they have a work journal of some kind where they document things in greater detail. It'd only be useful for them and nobody else. I guess it's the fear of losing their job to somebody who could read the documents and take over. It's not a crazy thought, but a business would prefer not to pay for someone to solve a problem that's already been solved. If only the previous person or team was willing to share, we could be using the time for other problems.

In this writeup, I'm looking at the runbook. Every team shoud have a runbook that covers their responsibilities from start to finish. A runbook is only half the battle but that half is pretty significant. The other half is execution. But you can’t execute if you don’t know what you are doing. I have worked with too many teams that do not have any basic troubleshooting documentations. I've been surprised when I ask "who is responsible for this piece of code?" and the response is…*crickets*. I understand that it's a large codebase or an extremely complex system but that's more the reason to document. I'll hear things like "we have documentation, look at this technical spellbook we used to build it." I'll look at it and respond, "yes, I took a look but this doesn't tell me what to do as an outsider. It doesn't even tell you what to do, and your team built this product and wrote this book! If it was useful, your team would not be calling us to help. At best, it tells me the obvious." They'll say "but you're from the reliability team, why can’t you fix this?" The answer is, because that's simply not how it works.

At a large NYC-based bank, we shifted to a "you build it, you run it" model in the recent years. It caused a lot of grumblings, as people thought this meant they have to play SRE or that they can't reach out to a SRE team for help. A SRE team is not a "fix-all solution" as we are often referred to as. A runbook is not, and should not, be a SRE-only tool. There is a reason why many large organizations will train its employees on basic medical and fire safety. Everybody knows the importance of these life saving skills. Nobody ever says "we can just call 911, why do we need to bother with this?" It's because while I can call my developers, I can take some mitigating steps to prevent the issues from getting worse. Even better if I can resolve the issue without ever calling them. If you have ever run into a situation where you felt helpless and thought "if only this was documented, we could have avoided all this," then you know exactly what I’m talking about. Most businesses prefer not to pay for hours that could've been avoided.

A runbook is a living document that should be regularly reviewed and updated. It is specific to the team, so no two runbooks are the same. It's so unique that the SRE team from the same company will have a very different runbook than another SRE team from the same company. Let’s jump in and build a toy runbook. You may fill in the gaps that are specific to your organization and your team:

1. First, start by asking what documents exist. Are they up-to-date? Can a new employee read these documents and start working?

2. If you have documentations, do you need to reduce them? If it's thousands of pages or poorly written, you have to ask if you can lower the complexity or rewrite it (that's a topic for another day.)

3. If you don't (or it's minimal), start by identifying gaps. What are some common problems the team faces on a regular basis?

4. What is your single source of truth (abbreviated SSoR?) At a large NYC organization I was at, the Terminal was our source of truth. At other places I've worked for, we used ServiceNow (or Snow.) If you do not have one, decide on that. It's not optional. It could be Confluence, or Jira, or even markdown. It could even be a CMS using Drupal. Whatever you decide on, the runbook must be able to reference it and vice versa.

5. Can you get buy-in from leadership and management?

6. If your team's work impacts other teams, do the other teams agree on the above? Are they aware?

Once you’ve identified these parts, your table of content and outline could look something like this:

1. Introduction
  - Scope
  - Audience
  - Version

2. Overview of Application / System / Process
  - Description
  - Architecture
  - Components and Dependencies

3. Roles
  - Team Structure
  - Contact
  - Escalation Steps

4. Monitoring
  - Alerts
  - Indicators
  - Rationale

5. Incident Management
  - Incident Classification
  - Incident Response Procedures

6. Appendices
  - Glossary
  - Reference

Keep in mind, the goal isn't page count. The goal is solving the technical or business problem that has occurred. Go into detail, but keep it so that whoever is reading it can get going. It's not necessary to write a grimoire. For example, you could include a section on the Splunk query that could assist with diagnosing the problem. The resulting output from the query could tell me if another app is causing impact to our app. Depending on use case, you can also include a customer impact count query. This is critical as you may need to report this figure to the legal authority. While the runbook may vary depending on the specific asset it needs to support, the general idea should be applicable no matter what organization you are in. Whether it's Apple or Meta, they need to know what to do when one of their apps go down. Another reason why you want a runbook is because this reduces cost. You don't need to hire people with decades of experience when you can bring in somebody junior at a fraction of the cost. As long as they can read and follow the runbook, they should be able to do the job. There is another type of runbook which is used for automaton and orchestration tools. It’s typically written in YAML or JSON and is used for routine workflow. I may explore this in the future, so please stay tuned!

‍
‍
Sifer Aseph

Cybersecurity Engineer @ Nyedis
