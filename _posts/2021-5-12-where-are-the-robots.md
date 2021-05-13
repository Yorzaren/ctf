---
title: "where are the robots"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - web exploitation
---

Problem: Can you find the robots? https://2019shell1.picoctf.com/problem/45102/ (link) or http://2019shell1.picoctf.com:45102

Solution: Going to the link you are greeted with a black page asking where are the robots.

Looking at the page source you'll find nothing. So where do any sites deal with robots? The robots.txt

Typing in https://2019shell1.picoctf.com/problem/45102/robots.txt

You'll see something ```Disallow: /8e32f.html``` check that out.

```
Guess you found the robots
picoCTF{ca1cu1at1ng_Mach1n3s_8e32f}
```

And there's the flag.

Flag: ```picoCTF{ca1cu1at1ng_Mach1n3s_8e32f}```