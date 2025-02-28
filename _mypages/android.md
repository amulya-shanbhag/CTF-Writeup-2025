---
title: "Android"
layout: default
---

<h2>Android</h2>

1. **That's a lot** - _What animal was in the TikTok sent via text?_  
 **Flag**:  <span style="color:red">Deer</span>  

 For the texts sent, looked under the android messages section of the android image and searched with keyword "tiktok", opened the link and there were Deers as also seen from the reply to tiktok text. 
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="IP Address" style="width:600px; height:auto;">  

2. **When you C it** - _What was the name of the geocacheing app used_?  
 **Flag**: <span style="color:red">C:geo</span>  

 Searched keyword "geocaching", the playstore application came up in the searched and display name was right there.
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/geocaching.png" alt="App Name" style="width:600px; height:auto;">  

3. **Finding a good book** - _What location was the user looking for on 2024-11-11 at 2:46:10 PM UTC?_  
 **Flag**: <span style="color:red">library champlain college</span>  

 For location I started looking at the Google maps search logs from Axiom Location & Travel section, also from the clue I was looking for something related to "book" where there was only search for champlain college library 
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/Library.png" alt="Library" style="width:600px; height:auto;">  

4. **Get in Contact** - _What is the users TikTok username?_  
 **Flag**: <span style="color:red">mary.jones7358</span>

 Searched with tiktok and found the username in tiktok contacts - social networking section in Axiom
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/username.png" alt="username" style="width:600px; height:auto;">  

5. **Highspeed Internet** - _What is the SIM display name?_  
 **Flag**: <span style="color:red">Ultra</span>  

 Searched with keyword "sim" and that displayed android sim card information
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/sim.png" alt="SIM name" style="width:600px; height:auto;">  

6. **Some Connections** - _What device did the user connect to on 2024-11-05?_  
 **Flag**: <span style="color:red">Google Pixel Watch 02N0</span>  

 Searched with the keyword "connected" to see if there were any such email or notifications. In the email on 2024-11-05, email from Google pixel was recieved, but wasn't sure if from the email if it was connected to the device. 
 Further searched "Google Pixel" and under bluetooth devices was the connection on the same day.
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/pixel.png" alt="Email" style="width:600px; height:auto;">  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/pixel2.png" alt="Bluetooth" style="width:600px; height:auto;">  

7. **The Era of Pop Stars** - _What song was the user listening to on 2024-11-30 at 8:45:00 AM?_  
 **Flag**: <span style="color:red">Fortnight</span>   

 Spent some time looking for the right path in axiom, had no luck and checked the aLeapp report - Recent Activity_0.html - 
 File path: \data\user\0\com.google.android.as\databases\history_db
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/fortnight.png" alt="Fortnight" style="width:600px; height:auto;">  

8. **Get Educated**- _What degree does Mary have?_  
 **Flag**:  <span style="color:red">Associate of Applied Science Marketing</span>  

 Had extracted Mary's resume in previous challenges which also mentioned her degree
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/degree.png" alt="Degree" style="width:600px; height:auto;">  

9. **That would look good in a Frame** - _What is the name of the structure seen in the picture taken at night?_  
 **Flag**: <span style="color:red">Moran Frame</span>    

 For the pictures taken, I checked the Google photos on aLeapp which did not give me the original picture, and as android photos are stored under dcim, I performed a search with dcim and downloaded the original picture from Axiom image. I tried all other names on the structure. I zoomed into the picture and found "Moran" written in light gray. Entered Moran as flag and that was wrong.
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/moranframe.png" alt="logs" style="width:600px; height:auto;">  

 Further I extracted the exif data of the picture which gave me the location of the image taken - 44°28'53.7"N 73°13'25.3"W, Checked this out on google maps
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/moran2.png" alt="logs" style="width:600px; height:auto;"> <img src="/CTF-Writeup-2025/docs/assets/imagesa/moran3.png" alt="logs" style="width:600px; height:auto;">  

10. **I love Natur** - _What language was the nature website in?_  
 **Flag**: <span style="color:red">German</span>  
 I tried the answer from the clue given, googled "Natur" and it's German. 
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/german.png" alt="Language" style="width:600px; height:auto;">  

11. **Striking Some Keys** - _What singer appeared in a TikTok video watched on 2024-11-15 at 1:01:26 AM UTC?_  
 **Flag**: <span style="color:red">Teddy Swims</span>
 Tiktok media under Social networking section, looked for the video at the given time and there he was
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/teddy.png" alt="Teddy Swims" style="width:600px; height:auto;">  

13. **Wearing out your SNEAKER**S - _Who congratulated Mary on walking 10,000 steps?_  
 **Flag**: <span style="color:red">noreply@fitbit.com</span>  
 Searched "congrat" on Axiom and found email from fitbit congratulating Mary
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/congrats.png" alt="Fitbit" style="width:600px; height:auto;">  

14. **Lets Get Famous** - _How many followers does Mary have on TikTok?_  
 **Flag**:  <span style="color:red">0</span>  
 From the blog post, I got that the follower count for tiktok can be accessed from tiktok db - The Android TikTok app keeps message related data in SQLite databases located in the following path: _userdata/data/com.zhiliaoapp.musically/databases/_
 The databse file - db_im_contact - stored the users followers and following count
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/followers.png" alt="followers" style="width:600px; height:auto;">  


<h2>Android Takeout</h2>

1. **Deadpool?** - _When was the Mint Mobile advertisement watched? YYYY-MM-DD HH:MM:SS EST_  
 **Flag**:  <span style="color:red">2024-11-06 12:01:21</span>   
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

2. **Best job I ever had** - _When was the Senior Marketing Accociate job started? YYYY-MM_  
 **Flag**: <span style="color:red">2023-02</span>  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

3. **Tryhard** - _What was this users GPA?_  
 **Flag**: <span style="color:red">4.0</span>   
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

4. **That's not very nice of you** - _What is the secret message found in an important file?_  
 **Flag**: <span style="color:red">ihateruth</span>   
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

5. **Getting Healthy** - _What fitness membership did this user join?_  
 **Flag**: <span style="color:red">Fitbit</span>  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

6. **Weekly Cycle** - _What day of the week did the user join this membership?_  
 **Flag**: <span style="color:red">Tuesday</span>  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

7. **I think this IS LAND?** - _What was the closest trail to the picture of a body of water?_  
 **Flag**:  <span style="color:red">ISLAND LINE</span>  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

8. **Flashbang** -_ What is the switch on the bottom left of the "About ______" website for?_  
 **Flag**: <span style="color:red">Dark mode</span>  
 <img src="/CTF-Writeup-2025/docs/assets/imagesa/ipadd.png" alt="logs" style="width:600px; height:auto;">  

