---
layout: post
title: "Identity and Access Management"
categories: cybersecurity
tags: cybersecurity WAM 1Kosmo SSI DID
---

* TOC
{:toc}

##



Role
A label for a set of related responsibilities



CIAM for Customers & Consumers

B2B IAM for Partners and Supply Chain

Employee IAM for Workforce Access



Identity Server (On-Prem)



Centralize security controls around user and service identities

Presume no user is trustworthy unless proved otherwise

Ensure users set strong passwords and regularly update them

Limit privileged accounts

Improve user experience with email-, SMS-, or biometrics-based logins

Regularly conduct access audits to review, revoke, or restrict access

Adhere to regulatory compliances like GDPR, CCPA, HIPPA



reconciliation, which is pulling accounts in

provision, which is pushing accounts out

authN is where users prove their identity

2 common methods: SAML, OIDC (built on top of OAuth, which is an authZ protocol)

SAML is also used in authZ



identity governance

CA Identity Manager



OIM (Oracle Identity Manager)

OIM manages an identity's lifecycle

OID (Oracle Internet Directory)

OID is a LDAP implementation



JCA (Java Connector Architecture)



make sure they have GUID (Global Unique ID)

you'll want good planning to save, in the following order: time, money, avoid frustration



entitlement is something you have access to

access policy is what you have access to

SOA (service-oriented architecture)



authoritative source -> reconciliation -> CRUD -> identity profile -> resource profile for each id profile 



Managed Service Provider (MSP)



Passwordless authentication



DS (directory service) is a LDAP client



Imprivata



##



## Vendor

Microsoft

OneLogin

IBM

Oracle

Micro Focus

Thales

Ilantus

### SiteMinder

"SiteMinder is a software product that is used to manage and secure access to web applications and resources. The SiteMinder proxy is a component of the SiteMinder system that acts as a mediator between a client and a server, forwarding requests from clients to servers and returning responses from servers to clients. The proxy is typically used to provide an additional layer of security and to enable the SiteMinder system to perform various tasks such as authenticating users, enforcing access controls, and logging activity. The SiteMinder proxy can be configured to work with various types of web servers and applications, and is often used in enterprise environments to manage access to corporate resources."



Tool used for authentication purposes
Session persistence is maintained by SM



SM Federation Services

SM Policy Server



### Datawiza

https://docs.datawiza.com

Access Management as a Service (AMaaS)

they offer a no-code platform for implementing authn and authz

SSO for enterprise customers

integrate SSO with internal homegrown apps

use any identity platform like Microsoft and Okta/Auth0

claims to implement RBAC and ABAC



### [ForgeRock](https://www.afterlifesong.com/cybersecurity/2022/01/04/forgerock.html)

### Centrify

### [Wallix](https://www.afterlifesong.com/cybersecurity/2022/12/15/wallix.html)

### [1Kosmos](https://www.afterlifesong.com/cybersecurity/2022/12/19/1kosmos.html)

### Styra

### [Ping Identity](https://www.afterlifesong.com/cybersecurity/2021/12/03/ping-identity.html)

### [PlainID](https://www.afterlifesong.com/cybersecurity/2023/06/20/plainid.html)

## Passwords



## Digital Certificates



## Web Access Management

A form of identity management that controls access to web resources



## Self-Sovereign Identity



### Decentralized ID

Decentralized Platform

A decentralized platform means no one owns it

If a company owns it, it's not fully or truly decentralized


