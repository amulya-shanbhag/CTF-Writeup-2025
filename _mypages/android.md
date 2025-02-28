---
title: "Android"
layout: default
---

Prerequisites: Processed the IOS image using aLeapp and Magnet Axiom Examine.

<h2>Android</h2>

1.**That's a lot** - _What animal was in the TikTok sent via text?_  
**Flag**:  <span style="color:red">Deer</span>  

For the texts sent, looked under the android messages section of the android image and searched with keyword "tiktok", opened the link and there were Deers as also seen from the reply to tiktok text.  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/deer.png" alt="IP Address" style="width:600px; height:auto;">  

2.**When you C it** - _What was the name of the geocacheing app used_?  
**Flag**: <span style="color:red">C:geo</span>  

Searched keyword "geocaching", the playstore application came up in the searched and display name was right there.  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/geocaching.png" alt="App Name" style="width:600px; height:auto;">  

3.**Finding a good book** - _What location was the user looking for on 2024-11-11 at 2:46:10 PM UTC?_  
**Flag**: <span style="color:red">library champlain college</span>  

For location I started looking at the Google maps search logs from Axiom Location & Travel section, also from the clue I was looking for something related to "book" where there was only search for champlain college library  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/library.png" alt="Library" style="width:600px; height:auto;">  

4.**Get in Contact** - _What is the users TikTok username?_  
**Flag**: <span style="color:red">mary.jones7358</span>

Searched with tiktok and found the username in tiktok contacts - social networking section in Axiom  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/username.png" alt="username" style="width:600px; height:auto;">  

5.**Highspeed Internet** - _What is the SIM display name?_  
**Flag**: <span style="color:red">Ultra</span>  

Searched with keyword "sim" and that displayed android sim card information  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/sim.png" alt="SIM name" style="width:600px; height:auto;">  

6.**Some Connections** - _What device did the user connect to on 2024-11-05?_  
**Flag**: <span style="color:red">Google Pixel Watch 02N0</span>  

Searched with the keyword "connected" to see if there were any such email or notifications. In the email on 2024-11-05, email from Google pixel was recieved, but wasn't sure if from the email if it was connected to the device. 
Further searched "Google Pixel" and under bluetooth devices was the connection on the same day.
<img src="/CTF-Writeup-2025/docs/assets/imagesa/pixel.png" alt="Email" style="width:600px; height:auto;">  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/pixel2.png" alt="Bluetooth" style="width:600px; height:auto;">  

7.**The Era of Pop Stars** - _What song was the user listening to on 2024-11-30 at 8:45:00 AM?_  
**Flag**: <span style="color:red">Fortnight</span>   

Spent some time looking for the right path in axiom, had no luck and checked the aLeapp report - Recent Activity_0.html - 
File path: \data\user\0\com.google.android.as\databases\history_db
<img src="/CTF-Writeup-2025/docs/assets/imagesa/fortnight.png" alt="Fortnight" style="width:600px; height:auto;">  

8.**Get Educated**- _What degree does Mary have?_  
**Flag**:  <span style="color:red">Associate of Applied Science Marketing</span>  

Had extracted Mary's resume in previous challenges which also mentioned her degree
<img src="/CTF-Writeup-2025/docs/assets/imagesa/degree.png" alt="Degree" style="width:600px; height:auto;">  

9.**That would look good in a Frame** - _What is the name of the structure seen in the picture taken at night?_  
**Flag**: <span style="color:red">Moran Frame</span>    

For the pictures taken, I checked the Google photos on aLeapp which did not give me the original picture, and as android photos are stored under dcim, I performed a search with dcim and downloaded the original picture from Axiom image. I tried all other names on the structure. I zoomed into the picture and found "Moran" written in light gray. Entered Moran as flag and that was wrong.
<img src="/CTF-Writeup-2025/docs/assets/imagesa/Moranframe.png" alt="Moranimage" style="width:600px; height:auto;">  

Further I extracted the exif data of the picture which gave me the location of the image taken - 44°28'53.7"N 73°13'25.3"W, Checked this out on google maps  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/moran2.png" alt="structure" style="width:600px; height:auto;"> <img src="/CTF-Writeup-2025/docs/assets/imagesa/moran3.png" alt="maps" style="width:600px; height:auto;">  

10.**I love Natur** - _What language was the nature website in?_  
**Flag**: <span style="color:red">German</span>  

I tried the answer from the clue given, googled "Natur" and it's German. 
<img src="/CTF-Writeup-2025/docs/assets/imagesa/german.png" alt="Language" style="width:600px; height:auto;">  

11.**Striking Some Keys** - _What singer appeared in a TikTok video watched on 2024-11-15 at 1:01:26 AM UTC?_  
**Flag**: <span style="color:red">Teddy Swims</span>  

Tiktok media under Social networking section, looked for the video at the given time and there he was  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/teddy.png" alt="Teddy Swims" style="width:600px; height:auto;">  

12.**Wearing out your SNEAKER**S - _Who congratulated Mary on walking 10,000 steps?_  
**Flag**: <span style="color:red">noreply@fitbit.com</span>  

Searched "congrat" on Axiom and found email from fitbit congratulating Mary  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/congrats.png" alt="Fitbit" style="width:600px; height:auto;">  

13.**Lets Get Famous** - _How many followers does Mary have on TikTok?_  
**Flag**:  <span style="color:red">0</span>  

From the [abrignoni blogspot](https://abrignoni.blogspot.com/2018/11/finding-tiktok-messages-in-android.html), I got that the follower count for tiktok can be accessed from tiktok db - The Android TikTok app keeps message related data in SQLite databases located in the following path: _userdata/data/com.zhiliaoapp.musically/databases/_  
The databse file - db_im_contact - stored the users followers and following count  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/followers.png" alt="followers" style="width:600px; height:auto;">  

  
  
<h2>Android Takeout</h2>

1.**Deadpool?** - _When was the Mint Mobile advertisement watched? YYYY-MM-DD HH:MM:SS EST_  
**Flag**:  <span style="color:red">2024-11-06 12:01:21</span>   

For the ads watched, looked into the youtube history and searched keyword "mint", flag was right there.  
File path: _Takeout/YouTube and YouTube Music/history/watch-history.html_  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/mint.png" alt="Ad watched" style="width:600px; height:auto;">   

2.**Best job I ever had** - _When was the Senior Marketing Accociate job started? YYYY-MM_  
**Flag**: <span style="color:red">2023-02</span>  

Again from Mary's resume downloaded  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/jobstart.png" alt="start date" style="width:600px; height:auto;">  

3.**Tryhard** - _What was this users GPA?_  
**Flag**: <span style="color:red">4.0</span>   

I did not find this on Mary's resume and went on looking for documents stored in the Takeout/Drive/, found another file - Jones_Resume2024.docx abd the GPA was mentioned there.  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/gpa.png" alt="GPA" style="width:600px; height:auto;">  

4.**That's not very nice of you** - _What is the secret message found in an important file?_  
**Flag**: <span style="color:red">ihateruth</span>  

Another document in the drive folder contained the flag  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/hate.png" alt="Secret message" style="width:600px; height:auto;">  

5.**Getting Healthy** - _What fitness membership did this user join?_  
**Flag**: <span style="color:red">Fitbit</span>  

From the previous flags, the answer is Fitbit and also found in Takeout/Gemini/Fitbit/ folder  

6.**Weekly Cycle** - _What day of the week did the user join this membership?_  
**Flag**: <span style="color:red">Tuesday</span>

The path Takeout/Gemini/Fitbit/Your Profile contained a profile.csv which showed the membership date as 11/5/2024 which was Tuesday.  
However, at first I entered Sunday which is mentioned as start of the week and luckily has 2 attempts for this.  

<img src="/CTF-Writeup-2025/docs/assets/imagesa/profile.png" alt="Profile" style="width:600px; height:auto;">  

7.**I think this IS LAND?** - _What was the closest trail to the picture of a body of water?_  
**Flag**:  <span style="color:red">ISLAND LINE</span>

From the image in the takeout file, downloaded the image and extracted the exif data from the file and got location: 44 deg 29' 25.30" N, 73 deg 14' 4.99" W, looking for this on google maps closest trail to this is Island line trail.  

<img src="/CTF-Writeup-2025/docs/assets/imagesa/waterbody.png" alt="image" style="width:600px; height:auto;">   
<img src="/CTF-Writeup-2025/docs/assets/imagesa/waterbody2.png" alt="exif data" style="width:600px; height:auto;">   
<img src="/CTF-Writeup-2025/docs/assets/imagesa/waterbody3.png" alt="location" style="width:600px; height:auto;">   

8.**Flashbang** - _What is the switch on the bottom left of the "About ______" website for?_  
**Flag**: <span style="color:red">Dark mode</span>

I didn't understand what website I should be looking for, later I looked into the android image in axiom and was typing "about" and about_play displayed in search suggestions and clicked on it showed the url - https://support.google.com/googleplay/?p=about_play, checking out this website showed language on the bottom left and and slightly overlapped with dark mode sttings
<img src="/CTF-Writeup-2025/docs/assets/imagesa/aboutplay.png" alt="search" style="width:600px; height:auto;">  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/aboutplay2.png" alt="url" style="width:600px; height:auto;">  
<img src="/CTF-Writeup-2025/docs/assets/imagesa/about3.png" alt="dark mode" style="width:600px; height:auto;">  

