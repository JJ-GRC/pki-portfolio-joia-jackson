# Week 3 Reflection



1. What did you learn this week?
This week I learned how PKI actually works in practice — not just the theory but the real mechanics. I pulled live certificates from Google and GitHub, decoded them using OpenSSL, read every field, walked the chain of trust from the leaf certificate up through the intermediate to the root CA, and analyzed what happens when certificates are misconfigured. I also learned the difference between the three keys involved in a TLS connection — the public key, private key, and session key — and how they work together to establish a secure connection.

2. What concept was most challenging?
I said it before and I'll say it again, The most challenging part of this week was not the concepts — it was the tools. Working in Git Bash and PowerShell to execute the labs required navigating file paths, saving files correctly, and running OpenSSL commands in an environment that gives very little feedback when something goes wrong. Small issues like Notepad adding hidden formatting, OneDrive moving the Desktop folder, and files saving with the wrong names caused hours of troubleshooting. The PKI concepts themselves clicked quickly, but getting the labs to execute correctly in the command line was the real challenge this week.

3. Where does this concept appear in real-world systems?
PKI appears everywhere. Every HTTPS website uses it. Enterprise environments use internal CAs to issue certificates for employee devices, VPNs, and internal services. Code signing uses the same certificate structure to verify software hasn't been tampered with. Certificate misconfigurations are one of the most common causes of production outages — expired certificates, missing intermediates, and incorrect Extended Key Usage settings can take down websites, APIs, and internal systems instantly.

4. How would you explain this topic to a non-technical audience?
When you visit a website, your browser needs to verify it's actually talking to the real website and not an imposter. PKI is the system that makes that possible. A trusted third party called a Certificate Authority verifies the website's identity and issues them a digital ID card — called a certificate. Your browser already knows which Certificate Authorities to trust, so when a website shows its certificate your browser can verify it's legitimate without ever having met that website before. If anything looks wrong — the ID is expired, it's from an untrusted source, or it's been tampered with — your browser blocks the connection and warns you.

5. What questions remain?
Can I work in PKI without using command line tools?
Are there GUI based tools for certificate management in real jobs?
How much command line will I actually use day to day as an analyst versus an engineer?
If the root CA is so protected, who actually has access to it and how do they use it?

---


