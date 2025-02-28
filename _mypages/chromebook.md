---
title: "Chromebook"
layout: default
permalink: /mypages/chromebook/
---
<h2>Chromebook</h2>  

Prerequisites: Extracted the tar file and processed the chromebook image using cLeapp and Magnet Axiom Examine.  

1.**Feeling: Connected** - _What was the ip address of the Chromebook?_ (5)   
  **Flag**: <span style="color:red">172.19.70.25</span>  
  
Found the device IP in chromebook network logs - /var/log/net.log 
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/ipadd.png" alt="logs" style="width:600px; height:auto;">  

2.**You used to call me on my cell phone** - _What number is stored in contacts? Format: +X (XXX) XXX-XXXX_ (5)  
  **Flag**: <span style="color:red">+18028292741</span>  
  
In Magnet axiom, android contacts under communication section shows only 1 contact number saved.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/contactnumber.png" alt="phone" style="width:600px; height:auto;">  

3.**Just five more minutes** - _How was the device most commonly woken up?_  (10)   
  **Flag**: <span style="color:red">Power Button</span>  
  
I was looking for eventlog file and In the cLeapp report index.html file, there is a section called Chrome OS event logs, searched for the wake source and sorted by detail. Power Button was most commonly used.  
  File path: temp\var\log\eventlog.txt  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/powerbutton.png" alt="wakesource" style="width:600px; height:auto;">  

4.**They'll hire anyone these days** - _How many months was Mary employed with her company?_  (10)  
  **Flag**: <span style="color:red">22</span>  
    
From Mary's resume found in the PDF documents, said they worked as a Senior Marketing Associate from 02/2023 - 11/2024, that's 22 months  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/hire.png" alt="employment" style="width:600px; height:auto;">  

5.**I got logged out** - _What string was autofilled the most?_ (10)  
  **Flag**: <span style="color:red">ruthonthego98@gmail.com</span>  
  
After reading through previous CTF writeups, I looked for the autofill entries in /home/user/Web Data and used DB Browser to check the autofill table.   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata.png" alt="Web Data" style="width:600px; height:auto;">  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/webdata2.png" alt="String" style="width:600px; height:auto;">  

6.**I definitely need new shoes** - _What is the size of Ruth's advertisement in bytes_ (10)  
  **Flag**: <span style="color:red">373,228</span>    

Searched advertise, which showed a compressed Marketing Advertisements.7z file and clicking on the source led to the user's Downloads folder and the flag  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach.png" alt="Ad Search" style="width:600px; height:auto;">   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/adserach2.png" alt="Flag" style="width:600px; height:auto;">  

7.**A for Anonymous** - _What TV show does Ruth have an interest in?_ (10)  
  **Flag**: <span style="color:red">Pretty Little Liars</span>    
  
There were multiple youtube and web searches for this TV show  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/pll.png" alt="TV SHOW" style="width:600px; height:auto;">  

8.**How'd your mic get so crispy?** - _What is the version of the noise supression software?_ (10)  
  **Flag**: <span style="color:red">253018</span>    

I did not know which noise supression software I should be looking for. From the clue, I googled crispy microphone and that showed an application called Krisp - a desktop app for noise cancellation.   
The answer was right there in the path, however I did not attempt the answer with that number, but followed the path which led me to the same version number.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp1.png" alt="Crisp" style="width:600px; height:auto;">   
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/crisp2.png" alt="Crisp 2" style="width:600px; height:auto;">   

9.**The start of an addiction** - _What date was the game installed on the system?_ (25)  
  **Flag**: <span style="color:red">11/16/2024</span>  
  
When looking for the previous flags, I came across clash royale game on Ruth's device and searched with clash, under Google Play Applications in Axiom Examine, you could get the application install date.  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/clashroyale.png" alt="Game App" style="width:600px; height:auto;">  

<h2>Chromebook Takeout</h2>

1.**Boorrriiiinnggg** - _What was searched 2024-11-12, 20:17:13 EST?_ (5)   
  **Flag**: <span style="color:red">iphone aesthetic wallpaper</span>  
  
The question was about searches, found the search activity in takeout folders path: _Takeout/My Activity/Search/_ and _Takeout/My Activity/Image Search/_ and found an Image search folder
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/wallpaper.png" alt="Search Keyword" style="width:600px; height:auto;">  

2.**Nice kicks** - _What is the name of the shoes created?_ (5)  
  **Flag**: <span style="color:red">floppers</span>  
  
From chromebook section, **I definitely need new shoes** - The shoes name was on the advertizement image, the same was searched on AI observed from the file _/Takeout/My Activity/Gemini Apps/MyActivity.html_  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/floppers.png" alt="Floppers" style="width:600px; height:auto;">

3.**Your shirt your way** - _What was the name of the shirt company?_ (5)  
  **Flag**: <span style="color:red">TypeShirt</span>   
  
In the same folder as the above flag, I searched with shirt which showed shirt company as Typeshirt  
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/typeshirt.png" alt="Shirt Company" style="width:600px; height:auto;">

4.**Shoe will have fun with this one** - _What is the shoe image named with file extension?_ (5)  
  **Flag**: <span style="color:red">f12cb76daad6c8d1.png</span>  
   
Looked for the above seen floppers image on Axiom and the file name was right there.
   <img src="/CTF-Writeup-2025/docs/assets/imagesc/shoename.png" alt="Shoe name" style="width:600px; height:auto;">  

5.**Identify yourself!** - _What is the account user ID?_ (5)  
  **Flag**: <span style="color:red">252838291214</span>  
  
Looked for the account information under the Google account folder - _/Takeout/Google Account/ruthonthego98.SubscriberInfo.html_ 
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/birthday.png" alt="Account ID" style="width:600px; height:auto;">  

6.**Back in my day** - _What was the users birthday? YYYY-MM-DD_ (5)  
  **Flag**: <span style="color:red">1998-12-18</span>
   
The same above file has the user's date of birth 

7.**King Town** - _What was the last app installed from the play store?_ (5)  
  **Flag**: <span style="color:red">Clash Royale</span>  
  
The information of play store application stored in json file _/Takeout/Google Play Store/Installs.json_ 
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/clashroyale.png" alt="Application" style="width:600px; height:auto;">

8.**Cat Nat** - _How long is the video watched on 2024-11-17 10:04:45 PM EST? Format: MM:SS_ (10)  
  **Flag**: <span style="color:red">29:24</span>  
  
For the video watched looked under the Youtube folder - _Takeout/YouTube and YouTube Music/history/watch-history.html_ and searched with time and opened the link and the video duration from youtube is the flag.
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/youtube.png" alt="Search" style="width:600px; height:auto;">
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/youtube2.png" alt="Youtube" style="width:600px; height:auto;">

9.**I need your approval** - _Who was the users boss? FIRSTNAME LASTNAME_ (10)   
  **Flag**: <span style="color:red">Gregory Fields</span>  
  
From the email coversations, the user's boss was asking for a document.
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/boss.png" alt="Boss Name" style="width:600px; height:auto;">

10.**Help I don't want to work!** - _What was the marketing website used after the shameless search?_ (10)   
  **Flag**: <span style="color:red">pipedrive.com</span>  
  
The question said marketing site used "after" the shameless search, found the related search, but found no marketing site after that timestamp, looked on google about pipedrive and that was the flag
  (https://www.google.com/url?q=http://www.pipedrive.com/en/gettingstarted-crm&usg=AOvVaw3ZyXGztGlGXtl0u1xTcI8q)
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/pipedrive.png" alt="Marketing site" style="width:600px; height:auto;">

11.**Stranger Danger**- _What was the IP address attatched to the sketchy email address?_ (10)  
  **Flag**: <span style="color:red">185.70.40.130</span>
  
There was an email hackergotyou@proton.me asking for ransom, checking the email headers showed the sender's IP
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/hackerip.png" alt="IPaddress" style="width:600px; height:auto;">

12.**Wandering Around** - _At the following time 2024-09-26 21:21:03 what was the geo location of the users IP Address? Country, State, City_ (10)  
  **Flag**: <span style="color:red">US,District of Columbia,Washington</span>  
  
I had observed this format on file _/Takeout/Google Account/ruthonthego98.SubscriberInfo.html_ after visiting it a multiple times for the previous flags 
  <img src="/CTF-Writeup-2025/docs/assets/imagesc/country.png" alt="country" style="width:600px; height:auto;">


