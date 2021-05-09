---
title: "First Grep: Part II"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: Can you find the flag in /problems/first-grep--part-ii_6_84224d7d745e41d24bde7e7bc7062bbe/files on the shell server? Remember to use grep.

Solution: Using the shell ```cd /problems/first-grep--part-ii_6_84224d7d745e41d24bde7e7bc7062bbe/files```

Theres a lot of files in folders. You need to check them all using grep. 

```cat */* | grep pico```

Flag: ```picoCTF{grep_r_to_find_this_5241c61f}```