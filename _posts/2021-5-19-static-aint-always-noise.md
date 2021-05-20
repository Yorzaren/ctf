---
title: "Static ain't always noise"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - general skills
---

Problem: Can you look at the data in this binary: static? This BASH script might help!

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/ltdis.sh "Download file")
File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/static "Download file")

Solution: HOW_TO

```
bash ltdis.sh static
```

Find the output file

```
cat static.ltdis.strings.txt | grep pico
```

Flag: ```picoCTF{d15a5m_t34s3r_f5aeda17}```