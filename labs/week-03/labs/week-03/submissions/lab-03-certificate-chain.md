# Lab 03 — Verify a Certificate Chain

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?
This lab was about pulling a live certificate chain from GitHub's server, saving each certificate separately, and verifying that the chain of trust connects correctly from the leaf certificate up to the root CA.
---

## Environment
- OS: Windows
- Terminal used (Mac Terminal / Git Bash / WSL): Gitbash
- OpenSSL version (`openssl version`): 3.6.1
- Website used: github.com

---

## Chain Verification Result
Paste the output of your `openssl verify` command: C=GB, O=Sectigo Limited, CN=Sectigo Public Server Authentication Root E46
error 2 at 2 depth lookup: unable to get issuer certificate
error server.pem: verification failed
The verification failed because the true root CA (USERTrust ECC Certification Authority) was not included in the output. The root.pem file contains an intermediate that is itself signed by USERTrust, which is pre-installed in browsers but not available as a standalone file from the server output.

---

## Certificate Roles
| Certificate | Subject | Issuer | CA:TRUE/FALSE |
|---|---|---|---|
| server.pem | CN=github.com | Sectigo Public Server Authentication CA DV E36 | CA:FALSE |
| intermediate.pem | Sectigo Public Server Authentication CA DV E36 | Sectigo Public Server Authentication Root E46 | CA:TRUE |
| root.pem | Sectigo Public Server Authentication Root E46 | USERTrust ECC Certification Authority | CA:TRUE |

---

## Observations

The root CA is USERTrust ECC Certification Authority — it is pre-installed in browsers and was not included in the server output.
The intermediate CA is Sectigo Public Server Authentication CA DV E36 — it was signed by the root and signs website certificates.
The leaf certificate is server.pem — issued directly to github.com with CA:FALSE.
The Issuer field connects the chain by pointing from each certificate up to the one that signed it. github.com's issuer is the intermediate CA, the intermediate's issuer is the root, and the root's issuer is USERTrust. Each link points to the next one up.
Intermediate certificates exist so the root CA doesn't have to sign every website certificate directly. The root is kept locked away and rarely used. If an intermediate CA is compromised it can be revoked without touching the root. It's an extra layer of protection for the most trusted part of the chain.
