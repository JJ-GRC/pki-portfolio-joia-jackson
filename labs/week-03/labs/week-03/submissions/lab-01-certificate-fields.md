# Lab 01 — Inspect X.509 Certificate Fields

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?
I pulled a real certificate from googles website and was able to see what was inside of it. 
Digital certificates and the chain of trust — specifically how a certificate contains the identity of the website, who issued it (the CA), and the public key, and how all of that gets verified before a secure connection is established.

---

## Environment
- OS: Windows 
- Terminal used (Mac Terminal / Git Bash / WSL): Git Bash
- OpenSSL version (`openssl version`):  OpenSSL 3.6.1 27 Jan 2026

---

## Certificate Fields

| Field                | Value from your output |
|----------------------|------------------------|
| Version              |   Version: 3                    
| Serial Number        |   7f:f3:2d:6b:40:9d:15:d5:96:5b:05:87:3a:7c:72:e0
| Signature Algorithm  |   ecdsa-with-SHA384                     
| Issuer               |   C=US, O=Google Trust Services LLC, CN=GTS Root R4                     
| Subject              |   google.com                     
| Not Before           |   Not Before: Dec 13 09:00:00 2023 GMT                     
| Not After            |   Not After : Feb 20 14:00:00 2029 GM                     
| Public Key Algorithm |   id-ecPublicKey                     

---

## Observations

1. Who issued the certificate? Google Trust Services LLC 
2. What domain or organization does it represent?
3. When does it expire? 2/20/29
4. What public key algorithm is used? id-ecPublicKey 
5. Why does the Issuer field matter in a PKI system? There's only a few CAs out there that are authorized to issue certificates, we need to make sure that the issuer is actually valid as well as the certificate. 
