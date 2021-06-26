---
title: "Snowboard"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Find the flag in the jpeg file. Good Luck!

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/Snowboard.jpg "Download file")

Solution: 

`exiftool Snowboard.jpg | grep {`

```
Comment                         : CTFlearn{CTFIsEasy!!!}.
```

Fake flag.

```
Current IPTC Digest             : 6cd3ab5fbec9aa23bd736996a08e8c96
```

Nothing of interest.

`strings -n 7 -t x Snowboard.jpg`

```
     18 CTFlearn{CTFIsEasy!!!}
     33 Q1RGbGVhcm57U2tpQmFuZmZ9Cg==
     ce Canon EOS 6D Mark II
     f4 GIMP 2.10.6
```

Looks like base64. 

Flag: `CTFlearn{SkiBanff}`