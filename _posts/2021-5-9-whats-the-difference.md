---
title: "whats-the-difference"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: Can you spot the difference? kitters cattos. They are also available at /problems/whats-the-difference_0_00862749a2aeb45993f36cc9cf98a47a on the shell server

File: [THE_FILE1](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/whats-the-difference-file1 "Download file")
[THE_FILE2](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/whats-the-difference-file2 "Download file")

Solution: cd into the directory then ```cmp kitters.jpg cattos.jpg -l -b``` then use the output to figure out the flag. 

Flag: ```picoCTF{th3yr3_a5_d1ff3r3nt_4s_bu773r_4nd_j311y_aslkjfdsalkfslkflkjdsfdszmz10548}```