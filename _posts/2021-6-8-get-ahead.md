---
title: "GET aHEAD"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
---

Problem: Find the flag being held on this server to get ahead of the competition http://mercury.picoctf.net:45028/

Hint 1: Maybe you have more than 2 choices

Hint 2: Check out tools like Burpsuite to modify your requests and look at the responses


Solution: 

Using Burpsuite you learn that clicking the red button sends the request as `GET` and clicking the blue one sends the request as `POST`. 

The title is the hint. You need to send the request as `HEAD`.

![no-alignment]({{ '/picoCTF-2021/solution-files/get-ahead.jpg' | absolute_url }})

Then you have the flag.

Flag: ```picoCTF{r3j3ct_th3_du4l1ty_775f2530}```