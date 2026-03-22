# Lab 02 — Investigate Certificate Extensions

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?
This lab was about pulling a real certificate from a live server and reading what's actually inside it. Using OpenSSL I connected to Google's server, extracted the certificate, and parsed it into a human-readable format to identify the key fields, who issued it, who it belongs to, what algorithm was used, and when it expires. PKI concept being investigated
The chain of trust.
---

## Environment
- OS: Windows
- Terminal used (Mac Terminal / Git Bash / WSL): Git Bash
- OpenSSL version (`openssl version`): 3.6.1

---

## Extensions Found

### Subject Alternative Name (SAN)
Paste the value from your output: I don't see anything

### Key Usage
Paste the value from your output: Digital Signature, Certificate Sign, CRL Sign

### Extended Key Usage (EKU)
Paste the value from your output: TLS Web Server Authentication, TLS Web Client Authentication

### Basic Constraints
Paste the value from your output: CA:TRUE, pathlen:0

---

## Observations

1. What domains appear in the SAN field? No domains appear in the SAN field
2. What operations are permitted by Key Usage? Key Usage permits digital signatures, signing other certificates, and signing certificate revocation lists (CRL Sign means it can publish lists of revoked certificates).
3. What applications are authorized by EKU? EKU authorizes this certificate to be used for TLS web server and web client authentication.
4. Can this certificate issue other certificates? How do you know? Yes it can issue other certificates — Basic Constraints says CA:TRUE. The pathlen:0 means it can sign end certificates but cannot create another intermediate CA below it.
5. Why are these extensions important for TLS validation? These extensions are important for TLS validation because they define exactly what a certificate is authorized to do. Without them a regular website certificate could claim to be a CA and start issuing fraudulent certificates. Extensions are how browsers enforce the rules of the chain of trust.
