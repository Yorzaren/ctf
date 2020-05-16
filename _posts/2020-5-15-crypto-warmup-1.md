---
title: "Crypto Warmup 1"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - cryptography
---

Problem: Crpyto can often be done by hand, here's a message you got from a friend, ```llkjmlmpadkkc``` with the key of ```thisisalilkey```. Can you use this table to solve it?.

File: [The table](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2018/problem-files/crypto-warmup-1.txt "Download file")

Solution: This is a Vigenere cipher. You can use the table for you can use an online solver. Like [https://www.boxentriq.com/code-breaking/vigenere-cipher](https://www.boxentriq.com/code-breaking/vigenere-cipher).

Flag: ```picoCTF{SECRETMESSAGE}```