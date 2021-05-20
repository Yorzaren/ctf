---
title: "Wave a flag"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - general skills
---

Problem: Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/problem-files/warm "Download file")

Solution: 

Make the file runnable.
```chmod 777 warm```

```./warm -h```

![no-alignment]({{ '/picoCTF-2021/solution-files/wave-a-flag.jpg' | absolute_url }})

Flag: ```picoCTF{b1scu1ts_4nd_gr4vy_616f7182}```