# Lab — [Lab Title]

## Overview
Briefly describe the purpose of this lab in your own words.  
What PKI concept or system behavior were you investigating?

---

## Environment
Document the environment used to complete the lab.

- Operating System:
- Terminal Used:
- OpenSSL Version (if applicable):

---

## Steps Performed
Summarize the key steps you performed to complete the lab.

Do **not copy the lab instructions**.  
Describe what you actually did.

1: Made a new folder (Directory) specifically for my hashing work so it doesn't get mixed up with my other files.
Command: mkdir C:\Users\Joia\labs\02-week-02-cryptography-fundamentals\submissions\hashes
2: Write these specific words and save them into a brand new file called message.txt 
3: Create the "Digital Fingerprint" (The Hash) openssl dgst -sha256 message.txt > message.sha256.txt
4: looked at the fingerprint cat message.sha256.txt
5: Save the "New Fingerprint" to a New File

---

## Results
Include the important outputs or findings from the lab.


---

## Key Findings
Document the most important observations from the lab.

I learned that if your change did in fact go through the file size will get bigger and to read the file using 
cat message.txt to see the last command. but this is still frustrating and not user friendly 

I can also see the original file and the change to the tampered one right under it 


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

These results matter so you can determine if a file has bee tampered with 

---

## Challenges / Troubleshooting
Document any issues encountered during the lab and how you resolved them.

It would be very helpful if the instructions were in this format to follow. I can't follow along easily. 
1: 
Step 1: Create a place to work
Command: mkdir C:\Users\Joia\labs\02-week-02-cryptography-fundamentals\submissions\hashes
What this tells PowerShell: "Make a new folder (Directory) specifically for my hashing work so it doesn't get mixed up with my other files."
Step 2: Move into that new folder
Command: cd C:\Users\Joia\labs\02-week-02-cryptography-fundamentals\submissions\hashes
What this tells PowerShell: "Change Directory. Take me inside the folder I just made so that everything I do next happens inside this room."
Step 3: Write your original message
Command: echo "Week 2 Hashing Lab - CVI" > message.txt
What this tells PowerShell: "Write these specific words and save them into a brand new file called message.txt."

2: It’s frustrating because the computer is just spitting out long strings of gibberish and expecting you to "spot the difference" yourself.

3: I don't like that you don't get any confirmation of what you did and if it was right. you just hit enter and that's it. I don't know if what i did was correct or not. 


---

## Artifacts
List the files generated during this lab.



---

CVI PKI Career Pathway — Foundations Phase
