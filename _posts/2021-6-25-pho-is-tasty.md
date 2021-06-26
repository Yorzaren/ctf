---
title: "Pho Is Tasty!"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

The flag is hidden in the jpeg file. Good Luck! Have some Pho! Solve this challenge before solving my Scope challenge for 100 points.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/Pho.jpg "Download file")

Solution: 

Tried exiftool, strings, binwalk

`bless Pho.jpg`

`43 04 15 54 02 06 46 14 0D 6C 16 0E 65 06 19 61 17 1F 72 1B 18 6E 01 0C 7B 04 07 49 0F 03 5F 02 0E 4C 16 18 6F 1F 04 76 19 0C 65 1F 06 5F 18 01 50 11 10 68 13 14 6F 1A 02 21 04 02 21 13 14 21 0B 14 7D`

or 

`CTF
learn{I_Love_Pho!!!}`

Remove everything but the letters.

Flag: `CTFlearn{I_Love_Pho!!!}`