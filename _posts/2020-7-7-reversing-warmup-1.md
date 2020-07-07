---
title: "Reversing Warmup 1"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - reversing
---

Problem: Throughout your journey you will have to run many programs. Can you navigate to /problems/reversing-warmup-1_0_f99f89de33522c93964bdec49fb2b838 on the shell server and run this [program](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2018/problem-files/reversing-warmup-1 "program") to retreive the flag?

Solution: Log in to the [shell](https://2018game.picoctf.com/shell) server. 

```cd /problems/reversing-warmup-1_0_f99f89de33522c93964bdec49fb2b838```

```ls```

to find what is there and there's a program named `run`.

```./run```

to execute the program.

Flag: ```picoCTF{welc0m3_t0_r3VeRs1nG}```