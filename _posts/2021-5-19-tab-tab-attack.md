---
title: "Tab, Tab, Attack"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - general skills
---

Problem: Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: Addadshashanammu.zip

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/Addadshashanammu.zip "Download file")

Solution: Unzip the file.

```
upzip Addadshashanammu.zip
```

```cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/```

```ls```

the file is runnable

```./fang-of-haynekhtnamet```

The program returns. ```*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}```

Flag: ```picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}```