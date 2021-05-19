---
title: "JaWT Scratchpad"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - web exploitation
---

Problem: Check the admin scratchpad! https://2019shell1.picoctf.com/problem/21893/ or http://2019shell1.picoctf.com:21893

Solution: When you attempt to login as ```admin``` you fail, but you can login as anything else. Checking the page you get a cookie.

```jwt``` set to ```eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiam9obiJ9._fAF3H23ckP4QtF1Po3epuZWxmbwpI8Q26hRPDTh32Y``` when login in as john.

https://jwt.io/ using this site you know that the algorithm is HS256 (HMAC with SHA-256). 

![no-alignment]({{ '/picoCTF-2019/solution-files/jawt-scratchpad.jpg' | absolute_url }})

Using john the rippper I'll toss the cookie string into a text file called crackthis.txt and using the wordlist rockyou.

```john crackthis.txt --format=HMAC-SHA256 --wordlist=/usr/share/wordlists/rockyou.txt```

![no-alignment]({{ '/picoCTF-2019/solution-files/jawt-scratchpad-2.jpg' | absolute_url }})

Cracked you get ```ilovepico```.

Going back to the jwt.io site you can edit the token to admin and change the verify signature to ilovepico.

![no-alignment]({{ '/picoCTF-2019/solution-files/jawt-scratchpad-3.jpg' | absolute_url }})

Edit the cookie to ```eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s``` refresh the page to get the flag.
![no-alignment]({{ '/picoCTF-2019/solution-files/jawt-scratchpad-4.jpg' | absolute_url }})

Flag: ```picoCTF{jawt_was_just_what_you_thought_c84a0d3754338763548dfc2dc171cdd0}```