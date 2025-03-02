---
title: "IOS"
layout: default
---

Prerequisites:
Processed the IOS image using iLeapp and Magnet Axiom Examine.

<h2>iOS</h2>

1.**Peak Performance** -- *What version of IOS* (5)<br/>
 **Flag**: <span style="color:red">18.0</span>  
 <br/>
 index.html file generated by iLeapp contained the iOS version <br/>  
 <img src="/CTF-Writeup-2025/docs/assets/iosversion.png" alt="IOS Version" style="width:600px; height:auto;">
 <br/>

2.**Connect The Digits** -- *What is the device's phone number?* (5)<br/>
 **Flag**: <span style="color:red">18024959063</span> 
 <br/>
 The same above report contained the device's phone number <br/>
 <img src="/CTF-Writeup-2025/docs/assets/IOSPhoneNumber.png" alt="phone number" style="width:600px; height:auto;">  
 <br/>

3.**In The Name of Friendship** -- *What was the contact name stored on 2024-11-13 5:45:05.000 PM* (5)<br/>
 **Flag**: <span style="color:red">MARY</span>   
 <br/>
 For stored contact information, I looked through the address book records in the iLeapp report, there was only one contact stored at the time. <br/>
 <img src="/CTF-Writeup-2025/docs/assets/Mary.png" alt="Mary" style="width:600px; height:auto;">  
 <br/>  
 
4.**Call Me, Maybe** -- *Out of all the incoming calls, how many were answered?* (5)<br/>
 **Flag**: <span style="color:red">0</span>     
 <br/>
 Call history in the iLeapp report showed multiple incoming call, but none answered. <br/>
 <img src="/CTF-Writeup-2025/docs/assets/callme.png" alt="Answered" style="width:600px; height:auto;">  
 <br/>
   
5.**Correct Me If I'm Wrong..** -- *How many words typed were autocorrected?* (10)<br/>
 **Flag**: <span style="color:red">51</span>   
 <br/>
 From the <a href="https://www.infosecinstitute.com/resources/digital-forensics/ios-forensics/" style="color: orange; text-decoration: underline;text-decoration-style: dotted;">infosec</a> , I learnt the keyboard caches contained in the file - /private/var/mobile/Library/Keyboard which contained user_model_database.sqlite<br/>  
 <img src="/CTF-Writeup-2025/docs/assets/autocorrected.png" alt="Auto correct" style="width:600px; height:auto;">    
 <br/>
   
6.**Where Are We Meeting?** -- *What time did ruth plan to meet Mary at Black Cap?* (10)   
**Flag**: <span style="color:red">2:15</span>     
<br/>
Searched the processed image on Magnet Examine with the name of coffee shop and answer was right there.  
<img src="/CTF-Writeup-2025/docs/assets/blackcapmeet.png" alt="Meet Time" style="width:600px; height:auto;">  
 <br/>
   
7.**The Root of The Problem** -- *What color hair does Ruth's Bitmoji have?* (10)   
 **Flag**: <span style="color:red">Blonde</span>   
 <br/>
 Looking at the media folder showed bitmoji image files one saved as "camera-lock-screen-widget-bitmoji".  
 <img src="/CTF-Writeup-2025/docs/assets/bitmojiblonde.png" alt="Hair colour" style="width:600px; height:auto;">  
 <br/>
   
8.**Artifically Crafted Designs** -- *What was the first AI tool installed on the device?* (10)  
 **Flag**: <span style="color:red">Canva</span>     
 <br/>
 In the ileapp report Installed apps -> itunes metadata - contains all the important details of applications installed on the user's device. Observed that Canva AI photo and Video editor was installed before ChatGPT  
 <img src="/CTF-Writeup-2025/docs/assets/Canva.png" alt="AI app" style="width:600px; height:auto;">  
 <br/>
    
9.**Tracing The Envelope** -- *What was the IP address logged from Discord?* (10)  
 **Flag**: <span style="color:red">184.171.159.153</span>   
 <br/>
 From the question "Tracing the envelope", looked into email section on Examine and found a security notification email from discord  
 <img src="/CTF-Writeup-2025/docs/assets/discordloginIP.png" alt="Discord login" style="width:600px; height:auto;">  
 <br/>
    
10.**Where's Nashville?** -- *What is the Latitude of Nashville in the Weather App? Format: xx.xxxxxxx* (10)   
 **Flag**: <span style="color:red">36.1660667</span>   
 <br/>
 I tried to look into examine logs by performing different searches but failed to get exact location, spent some time here and then checked the iLeapp report which logged Weather App Locations report  
 path - private\var\mobile\Containers\Shared\AppGroup\5A25F7AB-6542-44BF-BFF0-3A1B6E0EC1F1\Library\Preferences\group.com.apple.weather.plist  
 <img src="/CTF-Writeup-2025/docs/assets/locationnashville.png" alt="location" style="width:600px; height:auto;">  
 <br/>

11.**Important FACTor**- *What is the answer to second the equation in notes?* (25)   
**Flag**: <span style="color:red">432</span>     
 <br/>
 The question mentioned in notes and went through the Apple notes under Documents and submitted 216 as flag which turned out to be wrong. Luckily this question allowed multiple attempts.  
 <img src="/CTF-Writeup-2025/docs/assets/factor1.png" alt="Wrong answer" style="width:600px; height:auto;">  
 <br/>
 Further I found a <a href="https://medium.com/@mpotisambo8/ios-forensics-cheat-sheet-a121c74ef42d" style="color: orange; text-decoration: underline;text-decoration-style: dotted;">blog</a> for IOS cheatsheet and looked through /private/var/mobile/Containers/Shared/AppGroup/ where I found an image called Fallbackimage.png  
 <img src="/CTF-Writeup-2025/docs/assets/factor2.png" alt="Right" style="width:600px; height:auto;">   
 <br/>
    
12.**The Ghost That Couldn't Speak** -- *What app was denied permission to use Microphone?* (25)   
 **Flag**: <span style="color:red">Snapchat</span>     
 <br/>
 From Application permissions in iLeapp report, sorted the access column to show denied or not allowed actions and there - com.toyopagroup.picaboo was denied the Microphone access - Application is Snapchat  
 <img src="/CTF-Writeup-2025/docs/assets/snapchat.png" alt="Snapchat" style="width:600px; height:auto;">  
 <br/>
    
13.**The Sale Before the Sale** -- *If Ruth bought an item for $40 or more, she gets her second one 40% off with what code?* (25)  
 **Flag**: <span style="color:red">EARLYBF24</span>     
 <br/>
 In the iLeapp report I had come across this 40% off when looking for other flags and immediately digged into SMS section and entered 40%  
 path: private\var\mobile\Library\SMS\sms.db  
 <img src="/CTF-Writeup-2025/docs/assets/earlybf.png" alt="Code" style="width:600px; height:auto;">  
 <br/>
    
14.**TikTok on the Clock** -- *In YYYY-MM-DD HH:MM:SS format, when was the tiktok video posted?* (25)  
 **Flag**: <span style="color:red">2024-11-12 22:11:09</span>     
 <br/>
 The tiktok link from the chat - https://www.tiktok.com/@dochristmass/video/7436518844501347616?is_from_webapp=1&sender_device=pc - The number part in the URL itself seemed like datetime format. Looking for tools to break this I stumbled upon this site which   mentioned about unfurl - an open source tool for extracting URL   
 <img src="/CTF-Writeup-2025/docs/assets/unfurl.png" alt="Timestamp" style="width:600px; height:auto;">  
 <br/>
 Reference: [https://dfir.blog/tinkering-with-tiktok-timestamps/](url), [https://dfir.blog/unfurl/](url)  
 <br/>
    
15.**Directional Navigation** -- *What beach was searched for?* (25)  
 **Flag**: <span style="color:red">North Beach</span>     
 <br/>
 Believing I could find this in the ios maps, searched with keyword "beach" in the axiom evidence and showed multiple beaches. However, also found a discord chat which mentioned north beach park, tried out the flag North beach  
 <img src="/CTF-Writeup-2025/docs/assets/northbeach.png" alt="Beach" style="width:600px; height:auto;">  
 <br/>
    
16.**SERIALously Old!** -- *Using format YYYY-MM, When was this device purchased?* (25)  
 **Flag**: <span style="color:red">2022-12</span>     
 <br/>
 The clue was given as finding serial number, which I could easily fetch from the device details section in iLeapp report. However, I got diverted into checking the itunes metadata and later I came across a site where I could check the phone coverage which    showed me the purchase date  
 <img src="/CTF-Writeup-2025/docs/assets/serialnumber1.png" alt="Serial number" style="width:600px; height:auto;">  
 <img src="/CTF-Writeup-2025/docs/assets/purchasedate.png" alt="Purchase date" style="width:600px; height:auto;">  
 <br/>
    
17.**Artists write their names on the CANVAs** -- *Who is the author of the October 2023 wallpaper?* (25)    
 **Flag**: <span style="color:red">Nicole Vranjican</span>     
 <br/>
 Searched for wallpaper and found - October-2023-iphone-wallpaper-1170-×-2436-px-1.pdf , exported this to local system and used exiftool for this one and the author name right there.
 <img src="/CTF-Writeup-2025/docs/assets/nicole.png" alt="Author" style="width:600px; height:auto;">  
 <br/>
