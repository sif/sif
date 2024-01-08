---
layout: post
title: "Single Sign-On"
categories: cybersecurity
tags: cybersecurity
---

* TOC
{:toc}

## 

SLO single log-out



"One common example of SSO in the real world is when a user logs in to their corporate network using their Active Directory credentials. This allows them to access a variety of different applications and services without having to enter their username and password again for each one. Another example of SSO is when a user logs in to a social media platform, such as Facebook, and is then able to access a variety of different apps and services that are integrated with that platform without having to log in again."



OAuth vs SAML

IdP in SAML is Authorization Server in OAuth
SP in SAML is Resource Server in OAuth



"Federated SSO relies on open standards, including OAuth, WS-Federation, WS-Trust, OpenID Connect, and SAML to pass authentication tokens between organizations’ identity providers."
https://www.forgerock.com/platform/access-management/federation



Browser-based SSO

"Enables users to securely authenticate with multiple applications and websites by logging in only once."



SSO vs. FIM

"Although you may hear SSO and FIM frequently used together, they are not synonymous. Single sign-on enables access to applications and resources within a single domain. Federated identity management enables single-sign on to applications across multiple domains or organizations."
https://www.pingidentity.com/en/resources/blog/post/sso-vs-federated-identity-management.html 



ID token (JWT) is made of 3 parts: header, payload, signature



## OAuth 1.0

Deprecated in April 20, 2012



## OAuth 2.0, authorization

https://oauthdebugger.com

Use OAuth 2.0 with OIDC
you should NOT use OAuth for authentication

Use OAuth 2.0 for authorization:

- granting access to API
- getting access to user data in other systems

"A protocol for securing application access to protected resources by issuing access tokens to clients of Representational State Transfer (REST) APIs, and non-REST APIs."

- Resource owner
- Client
- Authorization server
- Resource server
- Authorization grant
- Redirection URI
- Access token
- Back channel (more secure channel, based on network security)
- Front channel (less secure channel, based on network security)

Problem with using OAuth 2.0 for authentication is that:

- no way to get the user's information
- every implementation is a little different
- no common set of scopes

But by using OIDC, OIDC brings to the table:

- ID token
- Userinfo endpoint for getting more user information
- Standard set of scopes
- Standardized implementation



### OAuth 2.0 flows

- Authorization code (front and back channel)
- Implicit (front channel only)
- Resource owner password credentials (back channel only)
- Client credentials (back channel only)



### OAuth 2.0 authorization code flow

- Client go to authorization server
- Authorization request consent from resource owner
- If no, then nothing but if yes, then back to redirect URI with authorization code
- Which client then uses to exchange for access code
- Client then gain access to resource server with access code



### Which grant type (flow) to use?

- Web application w/ server backend: authorization code flow
- Native mobile app: authorization code flow with PKCE
- JavaScript app (SPA) w/ API backend: implicit flow
- Microservices and APIs: client credentials flow



## OAuth 2.1

https://oauth.net/2.1/



## OAuth 3.0

does not exist, according to https://oauth.net/3/



## SAML (Security Assertion Markup Language)

SAML is XML based

it's a framework for exchanging security information between business partners (such as vendors)

it is based on the concept of assertions (statements about a user) which can be passed around

it provides a standard request/response protocol for exchanging XML messages

SAML provides portable trust, this means a user whose identity is established and verified in one domain, can invoke services in another domain

- cross-domain SSO, this means a user authenticate in one domain (say a website) and then is able to access resources in another domain (another website)
- federated identity, this means a set of service providers agrees on a way to refer to a single user even if they are known to each other under a different name

types of assertions:

- authentication
- authorization
- attributes

you can use SAML when you want external partners to submit a SAML payload to the organization's internal application

you can do the same in reverse

if I submit a SAML assertion, I am basically trying to prove my identity

"Security Assertion Markup Language (SAML) is an open standard that enables single sign-on (SSO)."

"SAML specifically enables identity federation, making it possible for identity providers (IdPs) to seamlessly and securely pass authenticated identities and their attributes to service providers (SPs)."



## Active Directory Federation Services (ADFS)



## OpenID Connect (OIDC), authentication

Use OIDC on top of OAuth 2.0 (which is on top of HTTP)

Use OIDC for authentication:

- logging the user in
- making your accounts available in other systems



## STS (secure token service)

WS-Trust Security Token Service (STS)
"A protocol for systems and applications to use when requesting a service to issue, validate, and exchange security tokens."



## IDAnywhere


