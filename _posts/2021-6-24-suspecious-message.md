---
title: "Suspecious message"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - cryptography
---

Hello! My friend Fari send me this suspecious message: 'MQDzqdor{Ix4Oa41W_1F_B00h_m1YlqPpPP}' and photo.png. Help me decrypt this!

[THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/photo.png "Download file")

Solution: 

The image is a 5x5 table and which is a playfair. 

```
QWERT
YUIOP
ASDFG
HKLZX
CVBNM
```

The table is the Encryption key: QWERTYUIOPASDFGHKLZXCVBNM

[Playfair](https://www.boxentriq.com/code-breaking/playfair-cipher)

Flag: `CTFLEARN{PL4YF41R_1S_C00L_C1PHERRRR}`