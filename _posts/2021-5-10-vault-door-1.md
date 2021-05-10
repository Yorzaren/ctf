---
title: "vault-door-1"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: VaultDoor1.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-1.java "Download file")

Solution: You will find the flag in sections. For me I found it easier to alpbetize the section and move parts of it in sections to be in the correct order and then strip it of the extra parts. 

```
password.charAt(0)  == 'd' &&
password.charAt(1)  == '3' &&
password.charAt(2)  == '5' &&
password.charAt(3)  == 'c' &&
password.charAt(4)  == 'r' &&
password.charAt(5)  == '4' &&
password.charAt(6)  == 'm' &&
password.charAt(7)  == 'b' &&
password.charAt(8)  == 'l' &&
password.charAt(9)  == '3' &&
password.charAt(10) == '_' &&
password.charAt(11) == 't' &&
password.charAt(12) == 'H' &&
password.charAt(13) == '3' &&
password.charAt(14) == '_' &&
password.charAt(15) == 'c' &&
password.charAt(16) == 'H' &&
password.charAt(17) == '4' &&
password.charAt(18) == 'r' &&
password.charAt(19) == '4' &&
password.charAt(20) == 'c' &&
password.charAt(21) == 'T' &&
password.charAt(22) == '3' &&
password.charAt(23) == 'r' &&
password.charAt(24) == '5' &&
password.charAt(25) == '_' &&
password.charAt(26) == '0' &&
password.charAt(27) == '3' &&
password.charAt(28) == 'b' &&
password.charAt(29) == '7' &&
password.charAt(30) == 'a' &&
password.charAt(31) == '0';
```

Strip using ```\(.+\)``` to remove the number part. And then remove the other uniform parts.

Flag: ```picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_03b7a0}```