Prerequisites: Extracted the tar file and processed the chromebook image using cLeapp and Magnet Axiom Examine.

---
title: Chromebook
---

1. **Feeling: Connected** - _What was the ip address of the Chromebook?_
**Flag**: 172.19.70.25  

Found the device IP in chromebook network logs - /var/log/net.log  

2. **You used to call me on my cell phone** - _What number is stored in contacts? Format: +X (XXX) XXX-XXXX_
**Flag**: +18028292741  

In Magnet axiom, android contacts under communication section shows only 1 contact number saved.  

3. **Just five more minutes** - _How was the device most commonly woken up?_  
**Flag**: Power Button  

I was looking for eventlog file and In the cLeapp report index.html file, there is a section called Chrome OS event logs, searched for the wake source and sorted by detail. Power Button was most commonly used.  
File path: temp\var\log\eventlog.txt  

4. **They'll hire anyone these days** - _ How many months was Mary employed with her company?_
Flag: 22

From Mary's resume found in the PDF documents, said they worked as a Senior Marketing Associate from 02/2023 - 11/2024, that's 22 months  

5. **I got logged out** - _What string was autofilled the most?_  
Flag: ruthonthego98@gmail.com  

After reading through previous CTF writeups, I looked for the autofill entries in /home/user/Web Data and used DB Browser to check the autofill table.   

6. **I definitely need new shoes** - _What is the size of Ruth's advertisement in bytes_  
Flag: 373,228  

Searched advertise, which showed a compressed Marketing Advertisements.7z file and clicking on the source led to the user's Downloads folder and the flag  

7. **A for Anonymous** - _What TV show does Ruth have an interest in?_
