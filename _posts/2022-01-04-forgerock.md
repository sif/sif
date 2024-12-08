---
layout: post
title: "Forgerock"
categories: cybersecurity
tags: cybersecurity
---

* TOC
{:toc}

bought out by Ping so if I ever get the time, I will need to transform this note

IAM, IGA, Passwordless CIAM, Workforce

Mule API Gateway



Identity Platform

ForgeRock Identity Platform offers access management, identity management, user-managed access, directory service, and an identity gateway



connector is a connection to external resources such as data store



nppi - non-public personal information



CIAM



## IDM (Identity Management)

what we see first

  - manages the lifecycle of identity
  - lets you provision and synchronize data



IDM password not hashed by default



IDM 7.4



### IG (Identity Governance)

ForgeRock Identity Governance is the IGA solution and designed to work with IDM

Needs the right OS, Java

Current IG (7.x.y) works with IDM 7.0, 7,1, 7.2, 7.3

Certification campaigns

Segregation-of-Duty (SOD) violation processes

Request administration



## AM (Access Management)

what customers see first

  - federation
  - create realm, set policies, user stores, etc.
  - create a flow with authentication trees

depending on how the organization deploys FR, if I am asked to federate with FR, I need to make it public



AM 7.4



### Amster

"Could not load library error when trying to run Amster after installing it for AM"
https://backstage.forgerock.com/knowledge/kb/article/a26732329



connect --interactive



export-config 



import-config



## DJ (or DS, Directory Service)

OpenDJ



DS 7.3.0 has been removed from backstage



## IGW (Identity Gateway)

Identity Gateway helps enable federation for applications that do not support SAML 2.0



## CTS (Core Token Service)

tokens stored inside LDAP, controlled by CTS



## Older Versions

will need custom run Java web app via class



create the said Java app, package the class as JAR, load the JAR file into a certain directory, drop the WAR (Web Application Archive) into Tomcat


