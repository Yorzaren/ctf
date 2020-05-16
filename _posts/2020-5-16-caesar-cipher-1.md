---
title: "caesar cipher 1"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - cryptography
---

Problem: This is one of the older ciphers in the books, can you decrypt the message? You can find the ciphertext in /problems/caesar-cipher-1_2_73ab1c3e92ea50396ad143ca48039b86 on the shell server.

File: [ciphertext](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2018/problem-files/caesar-cipher-1 "Download file")

Solution: Use a caesar cipher to decode it. You can shift the letters until you get some readable text. The key is 6.

Flag: ```picoCTF{justagoodoldcaesarcipherfwacbovv}```