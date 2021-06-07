---
title: "shark on wire 2"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - forensics
---

Problem: We found this packet capture. Recover the flag that was pilfered from the network. You can also find the file in /problems/shark-on-wire-2_0_3e92bfbdb2f6d0e25b8d019453fdbf07.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/shark-on-wire-2.pcap "Download file")

Solution: 

Checking the tcp stream doesnt do anything

Checking the udp stream. 

There's things that look like the flag but arent.

Continuing to check the stream you see something strange marked `start` at stream 32 and a bit later you see something marked `end` at stream 60.

Start comes from ```ip.src == 10.0.0.66```

The ports change for each of the packets.

```
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125
```

decimal to ascii 

`picoCTF{p1LLf3r3d_data_v1a_st3g0}`

Flag: ```picoCTF{p1LLf3r3d_data_v1a_st3g0}```