# Lab 04 — Detect Certificate Misconfigurations

## Overview
Briefly describe what this lab was about in your own words.
What PKI concept were you investigating?

---

## Scenario 1 — Missing Subject Alternative Name

**Would modern browsers trust this certificate?**
No. Modern browsers would reject this certificate even though the domain appears in the Common Name field.

**Analysis:**
Modern browsers require the SAN extension to be present in order to verify what domains a certificate is valid for. Chrome stopped trusting the Common Name field in 2017 and all major browsers followed. Even if a certificate only covers one domain, that domain must be explicitly listed in the SAN extension — the CN field alone is no longer sufficient for domain validation. In this scenario the certificate has CN=example.com in the subject but no SAN extension at all. The browser looks for the SAN extension during verification, finds nothing, and rejects the certificate. It does not fall back to the CN field.
The fix is straightforward — reissue the certificate with a SAN extension that lists the domain:
DNS:example.com
If the site also needs to work with www, both would be listed:
DNS:example.com, DNS:www.example.com
A user attempting to visit this site would see a "Your connection is not private" warning in Chrome with the error code NET::ERR_CERT_COMMON_NAME_INVALID.

---

## Scenario 2 — Incorrect Extended Key Usage

**Would a browser accept this certificate for a web server?**
A browser would reject this certificate because it is not authorized for web server use.

**Analysis:**
Extended Key Usage (Application Purpose) defines the specific real world contexts a certificate is authorized to be used in. It is the policy layer that restricts a certificate to its intended purpose — even if everything else about the certificate is valid, if the EKU doesn't match the use case the browser will reject it.
For HTTPS to work, a web server certificate must have TLS Web Server Authentication in the Extended Key Usage field. This tells the browser "this certificate was issued specifically for authenticating a web server." Without it the browser has no confirmation the certificate was intended for this purpose.
In this scenario the certificate has Client Authentication — meaning it was issued for a client to prove its identity to a server, not for a server to prove its identity to a browser. These are two different directions of authentication. The certificate is being used for the wrong job entirely.
The fix is to reissue the certificate with the correct Extended Key Usage value: TLS Web Server Authentication.
A user attempting to visit this site would see a "Your connection is not private" warning with an error indicating the certificate is not valid for this use.
---

## Scenario 3 — Expired Certificate

**What happens if this certificate is used today?**
The browser rejects the connection entirely. An expired certificate fails TLS validation immediately.

**Analysis:**

Every certificate has a validity period defined by two fields — Not Before and Not After. These dates are not suggestions. They are part of the certificate verification process and the browser checks them on every single connection. If the current date falls outside that window the certificate is considered invalid regardless of everything else being correct — the CA could be trusted, the chain could be complete, the signature could be valid, and it still gets rejected because the certificate is expired.
In this scenario the certificate expired on May 1 2023. Any connection attempt after that date fails validation automatically.
This is why certificate lifecycle management is critical in enterprise environments. Certificates expire and must be renewed before that date. A forgotten certificate on a production server can take down a website, an API, or an internal service instantly with no warning to users. Large organizations manage hundreds or thousands of certificates across their infrastructure — missing even one renewal can cause an outage.
A user attempting to visit this site would see a "Your connection is not private" warning in Chrome with the error code NET::ERR_CERT_DATE_INVALID. Most browsers do not give users an easy way to bypass an expired certificate — the connection is blocked.
---

## Scenario 4 — Missing Intermediate Certificate

**What error would a browser likely display?**
Most browsers would display a "Your connection is not private" error with an incomplete certificate chain warning. However browser behavior varies depending on how the browser handles missing intermediates.

**Analysis:**
Certificate chains establish trust by linking each certificate to the one above it. The leaf certificate is signed by the intermediate, the intermediate is signed by the root, and the root is pre-installed in the browser. The browser walks up this chain during verification — if any link is missing the chain breaks and trust cannot be established.
The intermediate certificate is not pre-installed in browsers the way root certificates are. This means the server is responsible for sending it along with the leaf certificate during the TLS handshake. If the server only sends the leaf certificate the browser receives it, looks for the intermediate to verify the signature, and can't find it.
Browser behavior varies at this point. Firefox strictly requires the full chain to be presented by the server and will reject the connection immediately with an SEC_ERROR_UNKNOWN_ISSUER error. Chrome has a feature called AIA fetching — it can follow the Authority Information Access URL embedded in the certificate and retrieve the missing intermediate automatically. This means Chrome users might connect successfully while Firefox users get an error from the exact same server.
This inconsistency is exactly why servers must always include the full chain. Relying on the browser to fetch missing pieces creates unpredictable behavior across different clients and is considered a misconfiguration.
The fix is to configure the server to send both the leaf certificate and the intermediate certificate together during the TLS handshake.
---

## Key Takeaway
In 2-3 sentences, explain why certificate misconfiguration is one of the most common causes of PKI outages.
