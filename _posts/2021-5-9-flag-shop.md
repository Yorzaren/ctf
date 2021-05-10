---
title: "flag_shop"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: There's a flag shop selling stuff, can you buy a flag? Source. Connect with nc 2019shell1.picoctf.com 3967.

Solution: ```nc 2019shell1.picoctf.com 3967```

It mentions 2s complement having something overflow so try to buy the flag, definitly not the flag flag and enter a large number like 4000000. It will cause the price of the flag to be a negative number giving you money to by the l337 flag. Buy the leet flag to get the flag.

Flag: ```picoCTF{m0n3y_bag5_cd0ead78}```