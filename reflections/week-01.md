# Week 1 Reflection

Submit this in your portfolio repository:
reflections/week-XX.md

---

## Prompts

What did you learn this week? 
  I learned about the overall flow of PKI. How a certificate is issued and what it's used for. 

What concept was most challenging? 
  Learning about the locks. I had to dig a little deeper to see who owns the lock, where it gets encrypted, who locks   it and different channels.

Where does this concept appear in real-world systems? 
  Every website you visit or system you interact with goes through this concept. It's everywhere. 

How would you explain this topic to a non-technical audience? 
  Lol I'm not technical, so this actually works for me. Anyone who wants to send information across the web and wants   people to trust them needs to get a certificate. The certificates come from CA's. Think of it like a school. CA's     have a root and intermediate. The principal is the root. He can't take care of all of the kids(sites) so he has       teachers (intermediates) The principal gives his approval for the teachers to take care of the kids. The teachers     check each kids birth certifcate to make sure they are who they say they are and once verified they give them the     stamp of approval and let them attend school. Once a business is good to go they send out their public key to         everyone. Anyone has access to this information. So say for instance, I visit walmart.com. Walmart.com sends to my    browser it's public key. My browser takes a look at the certificate, verifies the info on it and verifies the         intermedicate, CA and the root CA, says it's good to go and locks the data down and encrypts it before sending it     back to walmart. This way noone can intercept it while it's traveling on the internet and hack it. Once Walmart       receives it they have the code to unlock it and no one else, not even the original sender. What questions remain? 
  

