---
title: "Chromebook"
layout: default
permalink: /mypages/chromebook/
---
<h2>Chromebook</h2>  

Prerequisites: Extracted the tar file and processed the chromebook image using cLeapp and Magnet Axiom Examine.  

1.**Feeling: Connected** - _What was the ip address of the Chromebook?_  
**Flag**: <span style="color:red">172.19.70.25</span>  

Found the device IP in chromebook network logs - /var/log/net.log  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/ipadd.png" alt="logs" style="width:600px; height:auto;">  

2.**You used to call me on my cell phone** - _What number is stored in contacts? Format: +X (XXX) XXX-XXXX_  
**Flag**: <span style="color:red">+18028292741</span>  

In Magnet axiom, android contacts under communication section shows only 1 contact number saved.  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/contactnumber.png" alt="phone" style="width:600px; height:auto;">  

3.**Just five more minutes** - _How was the device most commonly woken up?_  
**Flag**: <span style="color:red">Power Button</span>  

I was looking for eventlog file and In the cLeapp report index.html file, there is a section called Chrome OS event logs, searched for the wake source and sorted by detail. Power Button was most commonly used.  
File path: temp\var\log\eventlog.txt  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/powerbutton.png" alt="wakesource" style="width:600px; height:auto;">  

4.**They'll hire anyone these days** - _How many months was Mary employed with her company?_  
**Flag**: <span style="color:red">22</span>  
  
From Mary's resume found in the PDF documents, said they worked as a Senior Marketing Associate from 02/2023 - 11/2024, that's 22 months  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/hire.png" alt="employment" style="width:600px; height:auto;">  

5.**I got logged out** - _What string was autofilled the most?_  
**Flag**: <span style="color:red">ruthonthego98@gmail.com</span>  

After reading through previous CTF writeups, I looked for the autofill entries in /home/user/Web Data and used DB Browser to check the autofill table.   
<img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata.png" alt="Web Data" style="width:600px; height:auto;">  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata2.png" alt="String" style="width:600px; height:auto;">  

6.**I definitely need new shoes** - _What is the size of Ruth's advertisement in bytes_  
**Flag**: <span style="color:red">373,228</span>    

Searched advertise, which showed a compressed Marketing Advertisements.7z file and clicking on the source led to the user's Downloads folder and the flag  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach.png" alt="Ad Search" style="width:600px; height:auto;">   
<img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach2.png" alt="Flag" style="width:600px; height:auto;">  

7.**A for Anonymous** - _What TV show does Ruth have an interest in?_  
**Flag**: <span style="color:red">Pretty Little Liars</span>    

There were multiple youtube and web searches for this TV show  
<img src="/CTF-Writeup-2025/docs/assets/imagesc/pll.png" alt="TV SHOW" style="width:600px; height:auto;">  

8.**How'd your mic get so crispy?** - _What is the version of the noise supression software?_  
  **Flag**: <span style="color:red">253018</span>    

  I did not know which noise supression software I should be looking for. From the clue, I googled crispy microphone and that showed an application called Krisp - a desktop app for noise cancellation.   
  The answer was right there in the path, however I did not attempt the answer with that number, but followed the path which led me to the same version number.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp1.png" alt="Crisp" style="width:600px; height:auto;">   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp2.png" alt="Crisp 2" style="width:600px; height:auto;">   

9.**The start of an addiction** - _What date was the game installed on the system?_  
  **Flag**: <span style="color:red">11/16/2024</span>  
  
  When looking for the previous flags, I came across clash royale game on Ruth's device and searched with clash, under Google Play Applications in Axiom Examine, you could get the application install date.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/clashroyale.png" alt="Game App" style="width:600px; height:auto;">  

<h2>Chromebook Takeout</h2>

1. **Boorrriiiinnggg** - _What was searched 2024-11-12, 20:17:13 EST?_  
  **Flag**: <span style="color:red">iphone aesthetic wallpaper</span>  

2. **Drive those ads away** - _What was the model of the Kia in the advertisement?_  
  **Flag**: <span style="color:red">2025 Sorento X-Pro SX-Prestige AWD</span>  

3. **Nice kicks** - _What is the name of the shoes created?_  
  **Flag**: <span style="color:red">floppers</span>  

4. **Your shirt your way** - _What was the name of the shirt company?_  
  **Flag**: <span style="color:red">TypeShirt</span>   

5. **Shoe will have fun with this one** - _What is the shoe image named with file extension?_  
  **Flag**: <span style="color:red">f12cb76daad6c8d1.png</span>   

6. **Identify yourself!** - _What is the account user ID?_  
  **Flag**: <span style="color:red">252838291214</span>  
  [file:///D:/Magnet%20CTF/Chromebook-20250206T193803Z-001/Chromebook/takeout-20241129T224833Z-001/Takeout/Google%20Account/ruthonthego98.SubscriberInfo.html](file:///D:/Magnet%20CTF/Chromebook-20250206T193803Z-001/Chromebook/takeout-20241129T224833Z-001/Takeout/Google%20Account/ruthonthego98.SubscriberInfo.html)  

7. **Back in my day** - _What was the users birthday? YYYY-MM-DD_  
  **Flag**: <span style="color:red">1998-12-18</span>  

8. **King Town** - _What was the last app installed from the play store?_  
  **Flag**: <span style="color:red">Clash Royale</span>  

9. **Cat Nat** - _How long is the video watched on 2024-11-17 10:04:45 PM EST? Format: MM:SS_  
  **Flag**: <span style="color:red">29:24</span>  

10. **I need your approval** - _Who was the users boss? FIRSTNAME LASTNAME_  
  **Flag**: <span style="color:red">Gregory Fields</span>  

11. **Help I don't want to work!** - _What was the marketing website used after the shameless search?_  
  **Flag**: <span style="color:red">[pipedrive.com]</span>  
  (https://www.google.com/url?q=http://www.pipedrive.com/en/gettingstarted-crm&usg=AOvVaw3ZyXGztGlGXtl0u1xTcI8q)

12. **Stranger Danger**- _What was the IP address attatched to the sketchy email address?_  
  **Flag**: <span style="color:red">185.70.40.130</span>  

13. **Wandering Around** - _At the following time 2024-09-26 21:21:03 what was the geo location of this users IP Address? Country, State, City_  
  **Flag**: <span style="color:red">US,District of Columbia,Washington</span>  







