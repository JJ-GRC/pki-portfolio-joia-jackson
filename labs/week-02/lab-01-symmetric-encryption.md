# Lab — [Lab Title]

## Overview
The purpose of this lab was to learn how to create a file, encrypt it, decrypt it and verify if the data was the same. 
What PKI concept or system behavior were you investigating?
The concept is symmetric encryption
---

## Environment
Document the environment used to complete the lab.

- Operating System: Windows 
- Terminal Used: Windows PowerShell
- OpenSSL Version (if applicable): 3.6.1

---

## Steps Performed
Summarize the key steps you performed to complete the lab.

Do **not copy the lab instructions**.  
Describe what you actually did.

1.  Created the "Master" Folder- C:\Users\Joia\labs\02-week-02-cryptography-fundamentals\submissions\encrypted

2.  Created the File Inside the master folder  New-Item -Path . -Name "plaintext.txt" -ItemType "file"

3.  Initiated the encryption by running the OpenSSL enc command

4.  Created a password - OpenSSL generated the 112-byte encrypted file: plaintext.txt.enc

5.  Entered the password you created in Step 2, and the file decrypted

6.  Ran ls to see the results. All three files existed, specifically noticing that your plaintext.decrypted.txt     matches   the original 80-byte size of your first file

 

---

## Results
Include the important outputs or findings from the lab.

assets/screenshots/assets/screenshots/week 2 lab 1.JPG


---

## Key Findings
Document the most important observations from the lab.

Verification of File Integrity-Since the byte counts match exactly, the decryption process successfully recovered the original data structure.


Examples:

- Certificate issuer
- Public key algorithm used
- Certificate extensions present
- Trust chain relationships
- Validation results

•  
•  
•  

---

## Explanation
Explain **why the results matter**.

Examples:

- Why the issuer is important in PKI
- Why SAN is required for modern TLS validation
- Why the certificate chain validates successfully
- Why a misconfiguration would cause a failure

---

## Challenges / Troubleshooting
Document any issues encountered during the lab and how you resolved them.
This lab was extremely difficult. The commands given didn't work and it took a god awful amount of time for me to figure out that copy and pasting them from the course was splitting the line and powershell wouldn't accept it. I had to use AI for majority of the assignment to give me the right commands. It was harder than it should have been. I also don't know where you would reference those commands in the future. Are they just known commands?

I also had a hard time with the password. I don't know why i couldn't get it to work and had to start over from ground 0 multiple times. This took HOURS to run one scan. Which left me defeated and frustrated. I didn't have time this week to move to lab 2 and 3. 

I can't get this template right. I copied it over for labs and it seemed to change format just fine. I do this one for reflections and it doesn't format correctly. I'm not sure why. 


Examples:

- command errors
- missing intermediate certificates
- verification failures

---

## Artifacts
List the files generated during this lab.

Examples:

- leaf_cert.pem
- server.pem
- intermediate.pem
- root.pem
- screenshots stored in assets/

---

CVI PKI Career Pathway — Foundations Phase
