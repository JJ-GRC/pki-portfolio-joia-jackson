 Week 2 Reflection


## Prompts

1. What did you learn this week?
I learned that powershell is a system to give commands to create items. I also learned the
rest of the TLS handshake.

I learned that the CA hashes the info in the certificate and locks it for authenticity based on 4 things ( name, public key, validity period and CA name) 

The difference between confidentiality, integrity, and authenticity-
Confidentiality is keeping items safe, integrity is making sure none of the information has been tampered with
and authenticity is making sure the right people have access to information

How symmetric encryption works-
symmetric encryption is one key. this usually follows asymmetric when a secure 
connection has been established to move information with speed. One exact key is shared amongst two parties to encrypt
and decrypt information. 

How hashing detects tampering- 
run a mathematical scan across both the file and digital signature to detect any 
differences whatsoever 

How digital signatures combine hashing and asymmetric cryptography-
when the server sends a public key to the browser 
and the browser checks the digital signature for authenticity- this includes name, validatiy dates, if the 
certificate has been revoked, etc. once that has been validated, then the browser runs a hash against the 
digital signature to see if it matches what's in the actual file. If all checks out it sends back a code and locks it. 
Then this is the start of symmetric cryptography to pick up speed. 

2. What concept was most challenging?
Powershell for sure.I couldn't get some things to work and after hours of chat I just gave up. I understand the 
concepts of TLS but I don't understand why I couldn't get my password to decrypt the file using the info you provided,
then chat gave me something else and it finally worked, but then comparing files i couldn't get it to unlock. this 
was the most frustrating process. Also it took me an ungodly amount of time to figure out that when copying and 
pasting the text provided it was separating onto two lines and not on one fluid line thus giving me a ton of 
error messages. 

3. Where does this concept appear in real-world systems?
My first thought goes to https connections. every website you visit goes through this TLS process, however it has
me thinking how many actual times this process happens througout one transaction from the user perspective. I
order a few items from amazon. Amazon doesn't sell products directly their just a marketplace. So not only is the 
connection between me and amazon, but amazon and each supplier plus amazon and visa plus visa and my bank. Depending
on what you are doing there could be hundreds of handshakes and plenty of opportunity to break through. Crazy.

4. How would you explain this topic to a non-technical audience?
Imagine you're sending a sealed envelope through the mail. Before you seal it, you weigh it on a very precise scale — down to the milligram — and write that weight on the outside.
When your friend receives it, they weigh it again before opening it. If the weight matches exactly, nothing was added or removed. If it's even slightly off, they know someone tampered with it.
That's a hash. Except instead of weight, it's a mathematical fingerprint of the data. And instead of "slightly off" — if anyone changes even one letter, the fingerprint looks completely different. Not close. Completely unrecognizable.


5. What questions remain?
Powershell is not easy for me to follow along. thank god for chat gpt bc the instructions and the format don't allow me to easily follow along. 
---


---












