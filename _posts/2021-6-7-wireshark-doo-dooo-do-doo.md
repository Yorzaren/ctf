---
title: "Wireshark doo dooo do doo..."
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - forensics
---

Problem: Can you find the flag? shark1.pcapng.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/shark1.pcapng "Download file")

Solution: 

Using wireshark I check the TCP streams on stream 5 I see something that might be the flag.

![no-alignment]({{ '/picoCTF-2021/solution-files/wireshark-doo-dooo-do-doo.jpg' | absolute_url }})

```Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}```

rot13 the string and you get the flag. ```The flag is picoCTF{p33kab00_1_s33_u_deadbeef}```

Flag: ```picoCTF{p33kab00_1_s33_u_deadbeef}```