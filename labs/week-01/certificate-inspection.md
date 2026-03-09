# Week 01 Lab — Certificate Inspection

## Screenshot Evidence

1. Capture a screenshot of the certificate details in your browser.
2. Save it as:

assets/screenshots/week-01/certificate-inspection.png

3. Embed the screenshot below:

![Certificate Inspection](../../assets/screenshots/week-01/certificate-inspection.png)


## Website Information

**Website inspected:**  
    www.google.com
  
**Issuer (Certificate Authority):**  
    Google Trust Services (Intermediate: WR2)
  
**Valid from:**  
    February 2, 2026
  
**Valid until:**  
    April 27, 2026
    
**Signature algorithm:**  
    SHA-256
---

## Subject Alternative Names (SAN Entries)

List at least 2–3 SAN entries:
    SAN entries are tucked inside the Extensions folder.
- 
- 
- 

---

## Observations

Document three observations about the certificate.

### Observation 1
  SAN entries are tucked inside the Extensions folder. I don't like that. Everything should be listed on the            certificate. 
  
### Observation 2
  Self-Managed CA: The issuer is "Google Trust Services," meaning Google acts as its own Certificate Authority rather   than using a third party like DigiCert
  
### Observation 3
  The validity period is short, about 2.5 months, which is consistent with modern best practices to reduce exposure     if a certificate is compromised.
---

## Reflection

Based on your inspection, explain how this certificate contributes to secure HTTPS communication.
  This certificate ensures that HTTPS connections to google.com and its subdomains are secure by enabling encrypted     communication between the browser and server. The certificate also authenticates that the server is genuinely         operated by Google, preventing man-in-the-middle attacks. Short-lived certificates and the use of strong              cryptographic algorithms (SHA-256) increase overall security and reduce vulnerability risk.
(2–3 sentences)
