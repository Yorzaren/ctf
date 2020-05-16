---
title: "Forensics Warmup 2"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - forencsics
  - file extensions
---

Problem: Can you unzip this file for me and retreive the flag?

File: [file.png](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2018/problem-files/forensics-warmup-2.png "Download file")

Solution: File has the wrong extension name. Its a jpg you can tell from the JFIF when editing the file. (Most image programs and web browsers can display files with the wrong extensions, regardles)

![no-alignment]({{ '/picoCTF-2018/solution-files/forensics-warmup-2-solution.jpg' | absolute_url }})

Flag: ```picoCTF{extensions_are_a_lie}```