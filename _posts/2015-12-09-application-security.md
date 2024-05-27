---
layout: post
title: "Application Security"
categories: cybersecurity
tags: cybersecurity appsec
---

* TOC
{:toc}

DAST

SAST

Semgrep

Application Security Posture Management (ASPM)
prioritizing application risk
AppSec control plane



cross-site request forgery



## Bug Hunting

- Have the software setup and ready to be used, make an account at the app you want to investigate, don't just look at the front-facing part of it
- Explore the software, ask for documentation (surprisingly, a lot of them don't have one)
- Pick a test area, then document the test cases covering normal and error conditions, then decide on the type of tests (unit, integration, system, stress, etc.)
- Look at automated testing (Selenium, JUnit, etc.)
- Look at manual testing
- If possible, figure out what's causing the bug (logic error, syntax mistake, resource issue, etc.)
- Document the findings and report it
- Regression testing once the bug has been fixed, check that the fix hasn't broken anything else

More in-depth testing includes pentesting, performance testing, etc.

Testing can also be included in the CI/CD pipeline



## Buffer Overflow

malware that used buffer overflow as part of their attack

Code Red (worm)

SQL Slammer (worm)



## Top 8 most common weaknesses (in order by pairs)

1. Security Misconfiguration
2. Access Control

3. Excessive Data Exposure
4. Insecure Cryptography

5. Insufficient Transport Layer Protection
6. Vulnerable Components

7. Information Exposure
8. Business Logic


