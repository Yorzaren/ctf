---
title: "Trivial Flag Transfer Protocol"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - forensics
---

Problem: Figure out how they moved the flag.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/tftp.pcapng "Download file")

Solution: 

Using wireshark check the objects TFTP files

instructions.txt
picture1.bmp
picture2.bmp
picture3.bmp
plan
program.deb

instructions.txt
```
GSGCQBRFAGRAPELCGBHEGENSSVPFBJRZHFGQVFTHVFRBHESYNTGENAFSRE.SVTHERBHGNJNLGBUVQRGURSYNTNAQVJVYYPURPXONPXSBEGURCYNA
```

Decode Caesar cipher key 13. Getting: tftp doesnt encrypt our traffic so we must disguise our flag transfer figure out away to hide the flag and i will check back for the plan

reading plan
```
VHFRQGURCEBTENZNAQUVQVGJVGU-QHRQVYVTRAPR.PURPXBHGGURCUBGBF
```
i used the program and hid it with due diligence check out the photos

Unpack the program ```alien -r program.deb```

Looks like its steghide which I already have.

run steghide using the password given in plan. ```DUEDILIGENCE``` with the caps and spacing back like the original.

```steghide --extract -sf picture1.bmp -f -p DUEDILIGENCE```
Nothing
```steghide --extract -sf picture2.bmp -f -p DUEDILIGENCE```
Nothing
```steghide --extract -sf picture3.bmp -f -p DUEDILIGENCE```
wrote extracted data to "flag.txt".

cat flag.txt
```
picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}
```

Flag: ```picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}```