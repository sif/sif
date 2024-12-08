---
layout: post
title: "Applied Cryptography"
categories: cybersecurity
tags: cybersecurity crypto
---

* TOC
{:toc}

Plain: A … Z

Cipher: map a letter (like A) first, then list the rest of the alphabet

cryptographic primitive includes:

- one-way hash
- encryption functions
- private key crypto, public key crypto
- digital signatures
- cryptographically secure pseudo-random number generator
- authentication
- mix network (onion routing such as Tor)



- symmetric encryption = private key
 asymmetric encryption = public key
- something is computationally indistinguishable if given a set of input, there is no result is uniform in time or rather the output is a negligible function
- non-malleable means they cannot mess with the ciphertexts
- Salting a password is important to protect against dictionary attacks and pre-computed rainbow attacks.



1
History of cryptography, some background in probability and algorithms, classical cryptography (shift cipher, monoalphabetic substitution cipher, polyalphabetic substitution cipher), encryption with perfect secrecy, one-time pad; implementation aspects: shared secret randomness vs perfect secrecy

2
Some background in algorithms and complexity theory, modern cryptography principles, one-way functions, trapdoor functions, hard-core bits, construction of a public-key cryptosystem based on general cryptographic primitives, implementation aspects: computational efficiency vs hardness

3
Algorithmic number theory, number theory and cryptographic assumptions, Reductions, proofs by reductions, number theory candidates for cryptographic primitives (e.g., factoring and related problems), public-key cryptosystems from number theory problems; brief discussion of quantum computing; implementation aspects: large integer arithmetic for implemented public-key cryptosystems

4
Randomness and pseudo-randomness, pseudo-random generators, functions and permutations. Symmetric encryption: introduction, security notions, symmetric encryption schemes based on pseudo-randomness primitives, security proofs, fundamental concepts; implementation aspects: generating and testing randomness

5
Symmetric encryption: block ciphers (e.g., DES, Triple-DES, AES), substitution/permutation networks, Feistel networks, modes of operations (e.g., ECB, CBC, OFB, Counter), cryptanalysis attacks (e.g., exhaustive, linear, differential, meet-in-the-middle attack), key lengths; implementation aspects: security-performance-features tradeoffs

6
Message authentication: introduction, notion and schemes (e.g., CBC-MAC), collision resistant hashing (MD5, SHA-1, SHA-2, SHA-3, HMAC, Merkle-Hellman), CCA security for symmetric encryption, simultaneous message confidentiality and message integrity, the GCM mode, application case study 1: password-based secure computer access; implementation aspects: security performance-features tradeoffs

7
More number theory candidates for cryptographic primitives (e.g., discrete logarithms, brief discussion of related problems including elliptic curves). Asymmetric encryption: comparison with symmetric encryption, definitions, constructions (e.g., RSA variants, El Gamal), hybrid encryption; implementation aspects: security-performance-features tradeoffs

8
Asymmetric encryption: malleable and homomorphic encryption notion and schemes (e.g., Paillier, brief discussion of various schemes, including Gentry’s), additional schemes achieving various security notions in various models (e.g., Cramer-Shoup), identity-based encryption; implementation aspects: security-performance-features-trust tradeoffs

9
Property-preserving public-key encryption, secure 2-party computation, secure multi party computation; application case study 2: sugar beet auction;implementation aspects of cryptographic protocols: transport layer, protocols over secure channels

10
Digital Signatures, hashing and signing, Hashed RSA, El Gamal and DSA signature schemes, public-key infrastructures, certificates, cryptography in TLS, IPSec and virtual private networks, NSA Suite B, application case study 3: secure online purchasing; implementation aspects: trust models, PKI implementation challenges

11
Key protocols: key transport, key agreement, notions and schemes (e.g., Diffie-Hellman schemes); key management: concepts and lifecycle; code obfuscation, application case study 4: digital rights management; quantum computing, quantum-resistant cryptography; implementation aspects: creating correct and secure programs, quality of code, side-channel attacks, implementation flaws

12
Key lengths and recommendations, user authentication: password, challenge-response and zero-knowledge protocols; server authentication; application case study 5: secure online banking; digital cash, application case study 6: keeping/storing secrets, blockchain, application case study 7: cryptocurrencies; implementation aspects: weakest key, key modularity



## Digital Certificate

used to verify user identity, which gives you nonrepudiation

- Version, most common is V1
- Serial
- Subject
- Algorithm ID
- Issuer
- Valid from/to
- Key usage
- Subject's public key
- Optional fields



## Public Key Infrastructure

A PKI manages digital certificates.

PKI uses asymmetric encryption and useful when passwords alone aren’t enough.

SSL is managed by PKI.

PKI lets you bind a public key (which is contained in the SSL certificate) to an entity, so you can trust it.


