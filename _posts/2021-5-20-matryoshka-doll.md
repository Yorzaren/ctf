---
title: "Matryoshka doll"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - forensics
---

Problem: Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: this

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/dolls.jpg "Download file")

Solution: 

```binwalk dolls.jpg -Me```

Like the name implies, the image has zip files within it eventually after unzipping it all you get a file marked: flag.txt

`cat flag.txt`

```picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}```

Flag: ```picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}```