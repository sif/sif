---
layout: post
title: "Software Development"
categories: software_engineering
tags: software_engineering methodology SM SDLC ATDD XP TDD BDD
---

* TOC
{:toc}

<img src="https://github.com/sif/sif/raw/main/files/post_files/scope.png" />



["Fred Brooks claimed in ‘The Mythical Man-Month’ that programmers working on the OS/360 operating system averaged around 10 LOC per day. Capers Jones measured productivity of around 16 to 38 LOC per day across a range of projects. McConnell measured productivity of 20 to 125 LOC per day for small projects (10,000 LOC) through to 1.5 to 25 LOC per day for large projects (10,000,000 LOC)."](https://successfulsoftware.net/2017/02/10/how-much-code-can-a-coder-code/)



http://thecodelesscode.com/



Working as designed (WAD)



Component
An element within a system



Calling Application (CA)



Technical debt (or code debt)



"Upstream refers to the material inputs needed for production, while downstream is the opposite end, where products get produced and distributed."

<img src="https://github.com/sif/sif/raw/main/files/post_files/production.png" />



## Software Development Life Cycle

Analysis -> Design -> Development -> Testing -> Deployment -> Maintenance



Consider use cases



### Software Documents

- SRS, Software Requirements Specification
- SPMP 
- SDD 
- RAS, Requirement Analysis Specification

- Functional Design Document
- Software Architecture Design Document
- Product Security Management Plan



## Methodologies

### Waterfall



### Agile

Incremental methods used in software development

https://twitter.com/AgileRamsay

"Uncle" Bob Martin - "The Future of Programming"
https://www.youtube.com/watch?v=ecIWPzGEbFc

Kanban
: A visual SDLC workflow process

Scrum master
: A developer who leads scrum meetings

Story
: Software system requirement

Active Sprint
: A sprint that has been started

User Story Designs (USD)

Definition of Done (DoD)

Epic
: Large body of work broken up into stories

#### Acceptance Test-Driven Development 



#### Extreme Programming



### Scrum

Scrum Flow

Scrum Theory

Scrum Team

Scrum Artifacts: Product Backlog

Scrum Artifacts: Increment

Scrum Events: Sprint Planning

Scrum Artifacts: Sprint Backlog

Scrum Events: The Sprint

Scrum Events: Development Work & Daily Scrum

Scrum Events: Sprint Review

Scrum Events: Sprint Retrospective

Scaled Scrum



### Lean



### Test-Driven Development



#### Behavior-Driven Development 



### Contract-First Development

Commonly used for web services and APIs
Goal is to understand the functionality before any implementation is done

Swagger (formerly OpenAPI)
tells the humans and computers to understand the service capabilities without access to source code, documentation, etc. 



Swagger Specification 2.0 

Swagger Specification 3.0



## Environments

Dev -> QA -> Staging -> UAT -> Production

CDE continuous delivery environment



## Clean Code

Naming variables

Writing functions



Guard clauses

```
# This function has no guard clause
def f_noguard(x):
    if isinstance(x, int):
        return x + 1

# Equivalent function with a guard clause
def f_guard(x):
    if not isinstance(x, int):
        return None
    return x + 1
```



## Testing

Release Acceptance Criteria (RAC)

Unit testing

Component testing

Contract testing

End-to-End Verification testing

Chaos testing

Performance testing

Visual testing

Automated testing

Integration testing

Smoke Testing is done to see if the build is stable enough before it is sent to the testing team for further testing

Shakeout Testing is done before the testing start to make sure that the applications are pointing to the correct environments/URLs and data is flowing

Sanity Testing is done whenever there is a small change made in the application to ensure that the application is working correctly

SIT system integration testing

UAT user acceptance testing
testing is done by end-user / client side, goal is to see if the solution delivered meets the business requirements for the customer

IST integration system testing
IST tests integration part or module of the application, goal is to verify if the technology works

UAT and IST are test environments

IST should come first, before UAT


