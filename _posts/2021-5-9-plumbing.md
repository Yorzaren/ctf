---
title: "plumbing"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to 2019shell1.picoctf.com 13203.

Solution: ```nc 2019shell1.picoctf.com 13203``` 

If you try connecting with out piping you'll see a lot of text thats not the flag telling you its not the flag. Disconnect and try using pipes to grep the flag out.

```nc 2019shell1.picoctf.com 13203 | grep pico```

Flag: ```picoCTF{digital_plumb3r_995d3c81}```