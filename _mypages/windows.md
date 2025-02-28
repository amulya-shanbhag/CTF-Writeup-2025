---
title: "Windows"
layout: default
---

<h2>Windows</h2>

1.**whoami?** - _What is the SID for the user "chick"?_  (5)  
**Flag**: <span style="color:red">S-1-5-21-493923485-410185161-2094537482-1001</span>  
 
The SID of users is stored in HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/SID.png" alt="SID" style="width:600px; height:auto;">  


2.**Goodbye!** - _When was the last logoff time for the user "chick"? (YYYY-MM-DD HH:MM:SS)_ (5)    
**Flag**: <span style="color:red">2024-11-24 17:36:55</span>  

In the Windows events logs, searched with the keyword "logged off" or could search with event id 4634 and sorted by the time.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/logoff.png" alt="Log off time" style="width:600px; height:auto;">  

3.**In the Zone** -  _What is the host URL that crow.jpg was downloaded from?_ (5)   
**Flag**: <span style="color:red">https://www.treehugger.com/thmb/EmZOvx28sGNqCtDqQQBMGv-aezM=/4288x2848/filters:fill(auto,1)/__opt__aboutcom__coeus__resources__content_migration__mnn__images__2019__10__american-crow-portrait-01-b3f0cfbdbf164de59831c9725bfdbf67.jpg</span>  

Searched with keyword "crow.jpg" and found the download source in the web related activities.   
<img src="/CTF-Writeup-2025/docs/assets/imagesw/crow.png" alt="Download Source" style="width:600px; height:auto;">  

4.**Sweet Find** - _What popular game was installed on the computer?_ (5)   
**Flag**: <span style="color:red">Candy Crush Saga</span>  

In the Installed Programs under Application Usage from the clue there was only one popular game. 
<img src="/CTF-Writeup-2025/docs/assets/imagesw/candy.png" alt="Game" style="width:600px; height:auto;">  

5.**Buried Treasure** - _On what social media platform did Mary look at a Burlington news account?_ (5)    
**Flag**: <span style="color:red">X</span>  

Performed a search with keyword "burlington" and I could see burlington freepress url which is a news platform, Operating system jump list url showed the source as Twitter, tried twitter on first attempt and then X  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/twitter.png" alt="X" style="width:600px; height:auto;"> 

6. **Follow the Thread** - _Where did Mary look for help with her coding questions?_ (5)    
**Flag**: <span style="color:red">reddit</span>  

Searched the keyword "coding" and under web related activities found multiple matches for coding with source as Reddit  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/coding.png" alt="Reddit" style="width:600px; height:auto;"> 

7. **Venomous Variables** - _What language was Mary's first program written in?_ (5)    
**Flag**: <span style="color:red">python</span>  

From the clue "venomous" I guessed it to be python.

8. **Account Registration** - _What is the creation date for Marys user account? (YYYY-MM-DD HH:MM:SS)_ (10)   
**Flag**: <span style="color:red">2024-09-24 15:11:51</span>  

In the Operating system, windows event logs searched with windows event 4720 for user creation
<img src="/CTF-Writeup-2025/docs/assets/imagesw/coding.png" alt="Reddit" style="width:600px; height:auto;"> 

9. **It's History Now** - _What was the name of the geocache that was completed?_ (10)   
**Flag**: <span style="color:red">Something's Fishy</span>  

Found this to be a little complicated, after multiple checks I googled to check if the geocache names are contained in the URL and found the below AI response.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/geocache.png" alt="Google search" style="width:600px; height:auto;">  

Further I searched GC / GPC and geocache on Axiom which showed the geocache name in the title.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/geocache2.png" alt="Google search" style="width:600px; height:auto;">  

10. **Where did it go?** - _What file was an anti-forensics tool used on?_ (10)   
**Flag**:  <span style="color:red">sucess.txt.txt</span>  

For this I also had to find out what was the antiforensics tool used and this took me some time and finally looking at the RTF Documents path, observed sdelete under the Users\chick\Downlaods file path.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/sdelete.png" alt="Anti-forenisics tool" style="width:600px; height:auto;">  

Searching "sdelete" further displayed the file that this tool was executed on.
<img src="/CTF-Writeup-2025/docs/assets/imagesw/sdelete2.png" alt="File Found" style="width:600px; height:auto;">  


11. **Used by only the PROs** - _What email service is Mary using other than gmail?_ (10)   
**Flag**: <span style="color:red">proton</span>  

From the previous hackergotyou protom mail was observed, searched "mail" in Axiom and under password and tokens showed the Protom mail signup service.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/proton.png" alt="Proton" style="width:600px; height:auto;">  

12. **A Stamped Link**- _What time was the tiktok that Mary watched posted? (YYYY-MM-DD HH:MM:SS UTC)_ (25)    
**Flag**: <span style="color:red">2024-11-12 22:11:09</span>  
  
https://www.tiktok.com/@dochristmass/video/7436518844501347616?is_from_webapp=1
Used [unfurl](https://dfir.blog/unfurl/) here  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/unfurl.png" alt="Unfurl" style="width:600px; height:auto;">

13. **Unravel the Mystery** - _What was the suggestion count when Mary was going to playing a popular word-based browser game?_ (25)  
**Flag**: <span style="color:red">12-6</span>  

Google searched "popular word games", among those I know wordle is popular and further seached "word" on axiom to confirm. I went into the site to check if I could find the number of hints, kept trying 6 over and over as I was pretty sure. But for a 25 points worth, started analysing the wordle URLs, just as I started in the 1st URL I observed number 6 and tracking back it was sc=12-6 , which makes the suggestion count 6. 

<img src="/CTF-Writeup-2025/docs/assets/imagesw/word.png" alt="Google Search" style="width:600px; height:auto;">  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/word2.png" alt="SC" style="width:600px; height:auto;">  

14. **Login Credentials Required** - What is Marys username on geocaching.com? (25)  
**Flag**:  <span style="color:red">geomaryr</span>  

While searching for the geocaching name, came across Google searches URL that contained the account username.  
<img src="/CTF-Writeup-2025/docs/assets/imagesw/geousername.png" alt="Geo Username" style="width:600px; height:auto;">  

