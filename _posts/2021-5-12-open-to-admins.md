---
title: "Open-to-admins"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - web exploitation
---

Problem: This secure website allows users to access the flag only if they are admin and if the time is exactly 1400. https://2019shell1.picoctf.com/problem/47265/ (link) or http://2019shell1.picoctf.com:47265

Solution: Edit the cookies setting admin to true and time to 1400. Then click the flag button to get the flag.

![no-alignment]({{ '/picoCTF-2019/solution-files/open-to-admins.jpg' | absolute_url }})
![no-alignment]({{ '/picoCTF-2019/solution-files/open-to-admins-2.jpg' | absolute_url }})


Flag: ```picoCTF{0p3n_t0_adm1n5_00cd0fe1}```