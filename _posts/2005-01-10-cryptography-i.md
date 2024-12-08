---
layout: post
title: "Cryptography I"
categories: cybersecurity
tags: cybersecurity crypto
---

* TOC
{:toc}

"Cryptology is the study of codes, both creating and solving them. Cryptography is the art of creating codes. Cryptanalysis is the art of surreptitiously revealing the contents of coded messages, breaking codes, that were not intended for you as a recipient."

<img src="https://github.com/sif/sif/raw/main/files/post_files/security.png" />



“Any computer system that requires password authentication must contain a database of passwords, either hashed or in plaintext, and various methods of password storage exist. Because the tables are vulnerable to theft, storing the plaintext password is dangerous. Most databases, therefore, store a cryptographic hash of a user's password in the database. In such a system, no one – including the authentication system – can determine what a user's password is by merely looking at the value stored in the database. Instead, when a user enters a password for authentication, it is hashed, and that output is compared to the stored entry for that user (which was hashed before being saved). If the two hashes match, access is granted. After gathering a password hash, using the said hash as a password would fail since the authentication system would hash it a second time. To learn a user's password, a password that produces the same hashed value must be found, usually through a brute-force or dictionary attack. Rainbow tables are one tool that has been developed to derive a password by looking only at a hashed value.”



## Hash

No hashing algorithm can guarantee absolute collision avoidance due to Pigeonhole Principle

Avalanche effect

- SHA-256 (Secure Hashing Algorithm) 
- MD5 128 bit hash, expressed as 32 bit hex
- SHA1
- SHA2



## Public Key Certificate

- X.509 (AES, PKCS, SSL/TLS)
- 



## Output

- RIPEMD 160-bit fixed output
- SHA-2 256-bit fixed output
- NTLM 128-bit fixed output
- MD-5 128-bit fixed output



## Salt



## HMAC



## Symmetric Encryption

Key pairs required



### Symmetric Algorithm

- DES 56-bit key (8-bit parity) fixed block
- 3DES 168-bit key, keys <= 3
- AES 128, 192, 256, replaced DES
- IDEA 128-bit key
- Twofish block cipher key size <= 256-bit
- Blowfish 64-bit block, replaced by AES
- RC 2040 key, includes RC2 -> RC6
- RC6 128-bit block

AES-CBC encryption mode available in XML Encryption 1.0 is vulnerable under certain conditions

XML Encryption 1.1 (2013) attempts to address this issue



## Key Pairs



## Asymmetric Encryption

Public key is used to encrypt, private key is used to decrypt



### Asymmetric Algorithm

- Diffie-Hellman used in SSL/IPSec
- ECC elliptical curve
- El Gamal 
- RSA 2x Prime 4,096 bit



## Signing



## Kerberos

- A ticket based system that allows many-to-many authentication, symmetric key crypto
- The strength of this is that it allows you to not have to store passwords. The issue is that you have to rely on trust of 3rd party.
- Typically used in corporate environments.
- Example: accessing the payroll department, you may request and be granted a ticket because of a recent promotion to view your salary detail. The ticket may last a week. 
- Kerberos is also known as a single sign on (SSO) system.
- KDC (key distribution center) is the part that deals with handling tickets and authentications
- TGS is ticket granting service which is a logical KDC component
- TGS validates the ticket for a specific purpose
- Policy makers in the organization deal with Kerberos. 

Kerberos basically stores a list of secret keys.



## TrueCrypt

- Create a partition or three. Depends on your need.
- Use TrueCrypt to create a partition within that, then use none for filesystem.
- Close TrueCrypt and open up a console. Format it to something by doing this: ./truecrypt --filesystem=none /dev/sdb1
- Then find the mapper in property of truecrypt after mounting with the first command: mke2fs -j -m0 /dev/mapper/truecrypt2



## Cryptoprocessor

Trusted execution environment (TEE) 
TEE is a secure area of the processor. It is a separate zone that allows the processor to isolate execution, provides application integrity and asset confidentiality. A real world example of TEE is TPM, trusted platform module.



## Attacks



dictionary attack

known plain-text: search plaintext for repeatable sequences, compare to t versions

ciphertext-only: obtain several messages with same algorithms, analyze to reveal repeating code

replay: performed in mitm, repeat exchange to fool system in setting up communication channel



51% attack



harvest now, decrypt later


