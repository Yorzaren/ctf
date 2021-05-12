---
title: "shark on wire 1"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - forensics
---

Problem: We found this packet capture. Recover the flag. You can also find the file in /problems/shark-on-wire-1_0_13d709ec13952807e477ba1b5404e620.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/shark-on-wire-1.pcap "Download file")

Solution: Using wireshark you follow the streams to get the flag. The first stream I checked has asdf letter spam so I continued checking until I came across the flag. 

![no-alignment]({{ '/picoCTF-2019/solution-files/shark-on-wire-1.jpg' | absolute_url }})


Flag: ```picoCTF{StaT31355_636f6e6e}```