---
title: "Magikarp Ground Mission"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - general skills
---

Problem: Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `ee388b88`

Solution: You use the instance and login. 

```cat 1of3.flag.txt```

```cat instructions-to-2of3.txt```

cd into the other directories and cat the remaining parts of the flag

![no-alignment]({{ '/picoCTF-2021/solution-files/magikarp-ground-mission.jpg' | absolute_url }})

Flag: ```picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}```