---
title: "First Grep"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: Can you find the flag in file? This would be really tedious to look through manually, something tells me there is a better way. You can also find the file in /problems/first-grep_5_452e1c1630eb14b6753e9a155c3ae588 on the shell server.


File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/first-grep "Download file")

Solution: Login into the shell and navigate to the file or download the file. Once in the directory. Type: ```cat file | grep pico```

Cat will print the contents of the file, but the file has a lot of text in it. So the best move is to use grep as the title of the problem implies. You use the | (pipe) to chain commands together.

Flag: ```picoCTF{grep_is_good_to_find_things_887251c6}```