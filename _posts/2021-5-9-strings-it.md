---
title: "strings it"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: Can you find the flag in file without running it? You can also find the file in /problems/strings-it_3_8386a6aa560aecfba03c0c6a550b5c51 on the shell server.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/string-it "Download file")

Solution: cd into the directory. Then run the command ```strings``` on the file named "strings". Like so.

```strings strings``` It will print out a lot of strings so lets find the flag using grep.

```strings strings | grep pico```


Flag: ```picoCTF{5tRIng5_1T_c7fff9e5}```