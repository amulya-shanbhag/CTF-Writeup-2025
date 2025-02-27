---
title: "Chromebook"
layout: default
permalink: /mypages/chromebook/
---

Prerequisites: Extracted the tar file and processed the chromebook image using cLeapp and Magnet Axiom Examine.  

1. **Feeling: Connected** - _What was the ip address of the Chromebook?_  
**Flag**: <span style="color:red">172.19.70.25</span>  

Found the device IP in chromebook network logs - /var/log/net.log  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/ipadd.png" alt="logs" style="width:600px; height:auto;">  

2. **You used to call me on my cell phone** - _What number is stored in contacts? Format: +X (XXX) XXX-XXXX_  
**Flag**: <span style="color:red">+18028292741</span>  

In Magnet axiom, android contacts under communication section shows only 1 contact number saved.  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/contactnumber.png" alt="phone" style="width:600px; height:auto;">  

3. **Just five more minutes** - _How was the device most commonly woken up?_  
  **Flag**: <span style="color:red">Power Button</span>  

  I was looking for eventlog file and In the cLeapp report index.html file, there is a section called Chrome OS event logs, searched for the wake source and sorted by detail. Power Button was most commonly used.  
  File path: temp\var\log\eventlog.txt  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/powerbutton.png" alt="wakesource" style="width:600px; height:auto;">  

4. **They'll hire anyone these days** - _How many months was Mary employed with her company?_  
  **Flag**: <span style="color:red">22</span>  
  
  From Mary's resume found in the PDF documents, said they worked as a Senior Marketing Associate from 02/2023 - 11/2024, that's 22 months  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/hire.png" alt="employment" style="width:600px; height:auto;">  

5. **I got logged out** - _What string was autofilled the most?_  
  **Flag**: <span style="color:red">ruthonthego98@gmail.com</span>  

  After reading through previous CTF writeups, I looked for the autofill entries in /home/user/Web Data and used DB Browser to check the autofill table.   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata.png" alt="Web Data" style="width:600px; height:auto;">  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata2.png" alt="String" style="width:600px; height:auto;">  

6. **I definitely need new shoes** - _What is the size of Ruth's advertisement in bytes_  
  **Flag**: <span style="color:red">373,228</span>    

  Searched advertise, which showed a compressed Marketing Advertisements.7z file and clicking on the source led to the user's Downloads folder and the flag  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach.png" alt="Ad Search" style="width:600px; height:auto;">   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach2.png" alt="Flag" style="width:600px; height:auto;">  

7. **A for Anonymous** - _What TV show does Ruth have an interest in?_  
  **Flag**: <span style="color:red">Pretty Little Liars</span>    

  There were multiple youtube and web searches for this TV show  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/pll.png" alt="TV SHOW" style="width:600px; height:auto;">  

8. **How'd your mic get so crispy?** - _What is the version of the noise supression software?_  
  **Flag**: <span style="color:red">253018</span>    

  I did not know which noise supression software I should be looking for. From the clue, I googled crispy microphone and that showed an application called Krisp - a desktop app for noise cancellation.   
  The answer was right there in the path, however I did not attempt the answer with that number, but followed the path which led me to the same version number.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp1.png" alt="Crisp" style="width:600px; height:auto;">   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp2.png" alt="Crisp 2" style="width:600px; height:auto;">   

9. **The start of an addiction** - _What date was the game installed on the system?_  
  **Flag**: <span style="color:red">11/16/2024</span>  
  
  When looking for the previous flags, I came across clash royale game on Ruth's device and searched with clash, under Google Play Applications in Axiom Examine, you could get the application install date.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/clashroyale.png" alt="Game App" style="width:600px; height:auto;">  











