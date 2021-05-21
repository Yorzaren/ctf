---
title: "information"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - forensics
---

Problem: Files can always be changed in a secret way. Can you find the flag? cat.jpg

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/cat.jpg "Download file")

Solution: Using an EXIF view you see 

```XMP
XMPToolkit	Image::ExifTool 10.80
License	cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights	PicoCTF
```

Decode `cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9` from base64 and you get the flag.

Flag: ```picoCTF{the_m3tadata_1s_modified}```