---
layout: post
title: "CS Topics Textbook Notes"
categories: books
tags: books
---

* TOC
{:toc}

## [Site Reliability Engineering](https://sre.google/books/)

Betsy Beyer, Chris Jones, Jennifer Petoff and Niall Richard Murphy

###  Preface

Reliability is the focus of SRE

"We like to think that Margaret Hamilton, working on the Apollo program on loan from MIT, had all of the significant traits of the first SRE. In her own words, "part of the culture was to learn from everyone and everything, including from that which one would least expect.""

"In addition to this great story, she also has a substantial claim to popularizing the term "software engineering.""

#### Facts and Fallacies of Software Engineering

Facts

People

Fact 1. The most important factor in software work is the quality of the programmers.

Fact 2. The best programmers are up to 28 times better than the worst programmers.

Fact 3. Adding people to a late project makes it later.

Fact 4. The working environment has a profound impact on productivity and quality.

Tools and Techniques

Fact 5. Hype (about tools and techniques) is the plague on the house of software.

Fact 6. New tools/techniques cause an initial loss of productivity/quality.

Fact 7. Software developers talk a lot about tools, but seldom use them.

Estimation

Fact 8. One of the two most common causes of runaway projects is poor estimation.

Fact 9. Software estimation usually occurs at the wrong time.

Fact 10. Software estimation is usually done by the wrong people.

Fact 11. Software estimates are rarely corrected as the project proceeds.

Fact 12. It is not surprising that software estimates are bad. But we live and die by them anyway!

Fact 13. There is a disconnect between software management and their programmers.

Fact 14. The answer to a feasibility study is almost always "yes".

Reuse

Fact 15. Reuse-in-the-small is a well-solved problem.

Fact 16. Reuse-in-the-large remains a mostly unsolved problem.

Fact 17. Reuse-in-the-large works best for families of related systems.

Fact 18. Reusable components are three times as hard to build, and should be tried out in three settings.

Fact 19. Modification of reused code is particularly error-prone.

Fact 20. Design pattern reuse is one solution to the problems of code reuse.

Complexity

Fact 21. For every 25 percent increase in problem complexity, there is a 100 percent increase in solution complexity.

Fact 22. Eighty percent of software work is intellectual. A fair amount of it is creative. Little of it is clerical.

Requirements

Fact 23. One of the two most common causes of runaway projects is unstable requirements.

Fact 24. Requirements errors are the most expensive to fix during production.

Fact 25. Missing requirements are the hardest requirements errors to correct.

Design

Fact 26. Explicit requirements "explode" as implicit (design) requirements for a solution evolve.

Fact 27. There is seldom one best design solution to a software problem.

Fact 28. Design is a complex, iterative process. Initial design solutions are usually wrong, and certainly not optimal.

Coding

Fact 29. Designer "primitives" (solutions they can readily code) rarely match programmer "primitives".

Fact 30. COBOL is a very bad language, but all the others (for business applications) are so much worse.

Error Removal

Fact 31. Error-removal is the most time-consuming phase of the life cycle.

Testing

Fact 32. Software is usually tested at best at the 55-60 percent (branch) coverage level.

Fact 33. 100 percent coverage is still far from enough.

Fact 34. Test tools are essential, but many are rarely used.

Fact 35. Test automation rarely is. Most testing activities cannot be automated.

Fact 36. Programmer-created, built-in, debug code is an important supplement to testing tools.

Reviews and Inspections

Fact 37. Rigorous inspections can remove up to 90 percent of errors before the first test case is run.

Fact 38. But rigorous inspections should not replace testing.

Fact 39. Post-delivery reviews (some call them "retrospectives") are important, and seldom performed.

Fact 40. Reviews are both technical and sociological, and both factors must be accommodated.

Maintenance.

Fact 41. Maintenance typically consumes 40-80 percent of software costs. It is probably the most important life cycle phase of software.

Fact 42. Enhancements represent roughly 60 percent of maintenance costs.

Fact 43. Maintenance is a solution, not a problem.

Fact 44. Understanding the existing product is the most difficult task of maintenance.

Fact 45. Better methods lead to MORE maintenance, not less.

Quality

Fact 46. Quality IS: a collection of attributes.

Fact 47. Quality is NOT: user satisfaction, meeting requirements, achieving cost/schedule, or reliability.

Reliability

Fact 48. There are errors that most programmers tend to make.

Fact 49. Errors tend to cluster.

Fact 50. There is no single best approach to software error removal.

Fact 51. Residual errors will always persist. The goal should be to minimize or eliminate severe errors.

Efficiency

Fact 52. Efficiency stems more from good design than good coding.

Fact 53. High-order-language code can be about 90 percent as efficient as comparable assembler code.

Fact 54. There are tradeoffs between size and time optimization.

Research

Fact 55. Many researchers advocate rather than investigate.

Fallacies

Management

Fallacy 1. You can't manage what you can't measure.

Fallacy 2. You can manage quality into a software product.

People

Fallacy 3. Programming can and should be egoless.

Tools and Techniques

Fallacy 4. Tools and techniques: one size fits all.

Fallacy 5. Software needs more methodologies.

Estimation

Fallacy 6. To estimate cost and schedule, first estimate lines of code.

Testing

Fallacy 7. Random test input is a good way to optimize testing.

Reviews

Fallacy 8. "Given enough eyeballs, all bugs are shallow".

Maintenance

Fallacy 9. The way to predict future maintenance cost and to make product replacement decisions is to look at past cost data.

Education

Fallacy 10. You teach people how to program by showing them how to write programs.

### Part I - Introduction

"Ben Treynor Sloss, the senior VP overseeing technical operations at Google—and the originator of the term "Site Reliability Engineering"—provides his view on what SRE means, how it works, and how it compares to other ways of doing things in the industry, in Introduction."

#### Chapter 1 - Introduction

"SRE is what happens when you ask a software engineer to design an operations team."

"Therefore, SRE is fundamentally doing work that has historically been done by an operations team, but using engineers with software expertise, and banking on the fact that these engineers are inherently both predisposed to, and have the ability to, design and implement automation with software to replace human labor."

"To avoid this fate, the team tasked with managing a service needs to code or it will drown. Therefore, Google places a 50% cap on the aggregate "ops" work for all SREs—tickets, on-call, manual tasks, etc."

"Google’s rule of thumb is that an SRE team must spend the remaining 50% of its time actually doing development."

“The term “DevOps” emerged in industry in late 2008 and as of this writing (early 2016) is still in a state of flux. Its core principles—involvement of the IT function in each phase of a system’s design and development, heavy reliance on automation versus human effort, the application of engineering practices and tools to operations tasks—are consistent with many of SRE’s principles and practices. One could view DevOps as a generalization of several core SRE principles to a wider range of organizations, management structures, and personnel. One could equivalently view SRE as a specific implementation of DevOps with some idiosyncratic extensions.”

"In general, an SRE team is responsible for the availability, latency, performance, efficiency, change management, monitoring, emergency response, and capacity planning of their service(s)."

"The error budget stems from the observation that 100% is the wrong reliability target for basically everything (pacemakers and anti-lock brakes being notable exceptions). In general, for any software service or system, 100% is not the right reliability target because no user can tell the difference between a system being 100% available and 99.999% available. There are many other systems in the path between user and service (their laptop, their home WiFi, their ISP, the power grid…) and those systems collectively are far less than 99.999% available. Thus, the marginal difference between 99.999% and 100% gets lost in the noise of other unavailability, and the user receives no benefit from the enormous effort required to add that last 0.001% of availability."

Monitoring
1. Alerts
2. Tickets
3. Logging

MTTF
MTTR

Change Management

Demand Forecasting and Capacity Planning

Provisioning

Efficiency and Performance

#### Chapter 2 - The Production Environment at Google, from the Viewpoint of an SRE

"Machine
A piece of hardware (or perhaps a VM)

Server
A piece of software that implements a service"

"Tens of machines are placed in a rack.
Racks stand in a row.
One or more rows form a cluster.
Usually a datacenter building houses multiple clusters.
Multiple datacenter buildings that are located close together form a campus."

<img src="https://github.com/sif/sif/raw/main/files/post_files/datacenter.jpg" />

"Machines within a given datacenter need to be able to talk with each other, so we created a very fast virtual switch with tens of thousands of ports. We accomplished this by connecting hundreds of Google-built switches in a Clos network fabric named Jupiter. In its largest configuration, Jupiter supports 1.3 Pbps bisection bandwidth among servers.

Datacenters are connected to each other with our globe-spanning backbone network B4. B4 is a software-defined networking architecture (and uses the OpenFlow open-standard communications protocol). It supplies massive bandwidth to a modest number of sites, and uses elastic bandwidth allocation to maximize average bandwidth."

"In a single cluster in a typical year, thousands of machines fail and thousands of hard disks break; when multiplied by the number of clusters we operate globally, these numbers become somewhat breathtaking."

"Borg, illustrated in Figure 2-2, is a distributed cluster operating system, similar to Apache Mesos. Borg manages its jobs at the cluster level."

<img src="https://github.com/sif/sif/raw/main/files/post_files/borg.jpg" />

binpack

Lustre, Hadoop Distributed File System (HDFS)

"Just as Borg limits the compute resources that a task can use, the Bandwidth Enforcer (BwE) manages the available bandwidth to maximize the average available bandwidth."

Global Software Load Balancer (GSLB)

protocol buffers

### Part II - Principles



#### Chapter 3 - Embracing Risk



## [The Site Reliability Workbook](https://sre.google/books/)

Betsy Beyer, Niall Richard Murphy, David K. Rensin, Kent Kawahara and Stephen Thorne

###



## [Building Secure and Reliable Systems](https://sre.google/books/)

Heather Adkins, Betsy Beyer, Paul Blankinship, Ana Oprea, Piotr Lewandowski, Adam Stubblefield

### 


