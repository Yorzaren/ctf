---
title: "extensions"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - forensics
---

Problem: This is a really weird text file TXT? Can you find the flag?

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/extensions.txt "Download file")

Solution: If you opened the file in a hex editor you'd notice the extension is ```89 50 4E 47``` meaning its a .png file. Or you could have attempted to open it as a txt file and noticed the PNG part with the unreadable characters. So change the file and then you can open it.

![no-alignment]({{ '/picoCTF-2019/solution-files/extensions.png' | absolute_url }})


Flag: ```picoCTF{now_you_know_about_extensions}```