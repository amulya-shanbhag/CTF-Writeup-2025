---
title: "My CTF Experience"
laoyout: default
---

<h2>Learn from my mistakes</h2>

The Magnet Forensics CTF Tools & Tips session, conducted by Jessica Hyde and Kevin Pagano, covered numerous tips for solving CTF challenges, common do’s and don’ts, and various strategies that proved invaluable during the competition.

As a first-time CTF participant, here are some key things that helped me answer many questions efficiently:

1.**Referring to previous years' CTF writeups** – This helped me understand the question patterns, had all the images pre-processed, and consolidated the most commonly used tools in one place.
2.**Pre-analyzing the provided images** – Before diving into questions, I conducted a quick overview to get a general understanding of the scenario and potential artifacts. Keeping notes would have been even more beneficial during the competition.
3.**Glancing through all questions first** – As soon as the competition started, I took a moment to scan the questions to identify sections where I felt most confident before attempting them.
4.**Prioritizing lower-point questions** – I started with the 5, 10, and 15-point questions first. If a question took too long, I moved on. Interestingly, I often found answers to earlier questions while working on later ones.
5.**Leveraging clues in the questions** – Many clues were hidden in the question itself. For example, the Android question: "What language is the website in?" included a pun: "I love Natur", hinting at "Nature" and the German language. However, I learned not to risk guesses when attempts were limited.
6.**Tracking correct flags** – Keeping a record of correct flags sometimes helps answering next questions.
7.**Staying calm and treating it as a fun learning experience** – Keeping a composed mindset significantly improved my problem-solving efficiency.

<h2>Challenges & Mistakes</h2>

1.**Spending too much time on misleading questions** – At times, I felt overly confident in my answer and kept digging into the same approach, wasting valuable time instead of moving on.
2.**Overlooking limited attempt restrictions** – I lost easy points on some questions because:
3.I missed the "limited attempts" note in the first such question.
4.I was too confident in my answer and didn't double-check before submitting.
5.**Getting discouraged by a tough start** – I was initially frustrated when I couldn't find the first flag of a section. However, once I moved on to the next questions, I gained momentum and solved them quickly.
6.**Overthinking easy questions** – Surprisingly, I answered 10, 15, and even some 25-point questions faster than the 5-point ones. This happened because I overanalyzed simpler questions instead of trusting my instincts

<h2>Some Facepalm moments</h2>

1.**Dressing, with a dash. of 17 spices** - Decode the secret message: https://drive.google.com/file/d/1UuqI4YZDbvZcieXE4-t5BhEqiPHsGkIC/view?usp=drive_link
**Flag**: LOCKEDOUT
There was morse code provided in the challenge and was the most easiest cipher challenge, I submitted a wrong answer at first and found the right flag after, but had only 1 attempt. Regret!!
<img src="/CTF-Writeup-2025/docs/assets/lockedout.png" alt="Locked out" style="width:600px; height:auto;">

2.**A Shadow of the Real Thing** -	What is the hashed password for the user “chick”?
For the hashed password, I exported SAM and SYSTEM and ran Impacket on them, retrieving the NTLM hash for the user - 1576adde2adbf62ec5a977a64ff753b6. However, this turned out to be incorrect.
From the clue "shadow", I immediately thought of the shadow file in Linux. Unfortunately, I didn’t think beyond that, even though the evidence contained a Kali VM. I was too fixated on my initial answer and only looked for a possible Windows hash, missing the Linux-based approach. 
<img src="/CTF-Writeup-2025/docs/assets/hash.png" alt="Locked out" style="width:600px; height:auto;">

<h2>Lessons Learned</h2>

1.**Prioritize Efficient Time Management**
-- Avoid spending too much time on a single question, especially when unsure. If stuck, move on and revisit later—answers may reveal themselves while solving other challenges.

2.**Read the Questions Carefully**
-- Many clues are hidden within the question itself. Pay attention to wording, puns, and hints that could lead to the correct approach.

3.**Be Mindful of Limited Attempts**
-- Always check whether a question has restricted attempts before submitting an answer. Avoid guessing blindly to prevent unnecessary losses.

4.**Stay Open-Minded**
-- If one method doesn’t work, rethink the approach instead of getting fixated on a wrong assumption. Consider multiple possibilities and alternate tools.

5.**Take a Step Back When Stuck**
-- Instead of forcing an incorrect answer, step away and reassess with a fresh perspective. Returning later may reveal overlooked details.

6.**Maintain Proper Notes & Track Flags**
-- Keeping structured notes would help recall steps taken, tools used, and approaches tested. Recording submitted flags prevents repeating failed attempts.

7.**Stay Calm and Have Fun!** 😃
A cool-headed approach leads to better problem-solving. Treating the CTF as a learning experience removes pressure and enhances overall performance.

