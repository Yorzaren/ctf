---
title: "Milkslap"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - forensics
---

Problem: 🥛 (http://mercury.picoctf.net:48380/)

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/concat_v.png "Download file")

Solution: 

Going to the site you can see an image of a man getting slapped with milk when you move your mouse.

Looking at the js and css you can see how it works. Looking at http://mercury.picoctf.net:48380/concat_v.png

This is the large image they use to make it work.

Checking the file 

```binwalk concat_v.png```

```strings concat_v.png | grep pico```

```exiv2 concat_v.png```

```zsteg concat_v.png```



![no-alignment]({{ '/picoCTF-2021/solution-files/milkslap.jpg' | absolute_url }})


Flag: ```picoCTF{imag3_m4n1pul4t10n_sl4p5}```