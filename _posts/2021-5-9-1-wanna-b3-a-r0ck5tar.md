---
title: "1_wanna_b3_a_r0ck5tar"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - general skills
---

Problem: I wrote you another song. Put the flag in the picoCTF{} flag format

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/1-wanna-b3-a-r0ck5tar.txt "Download file")

Solution: Install a transpiler for rockstar to python. Follow the instructions at the repo. https://github.com/yyyyyyyan/rockstar-py 

Running the transpiler you get the following code. 

```Rocknroll = True
Silence = False
a_guitar = 10
Tommy = 44
Music = 170
the_music = input()
if the_music == a_guitar:
    print("Keep on rocking!")
    the_rhythm = input()
    if the_rhythm - Music == False:
        Tommy = 66
        print(Tommy!)
        Music = 79
        Jamming = 78
        print(Music!)
        print(Jamming!)
        Tommy = 74
        print(Tommy!)
        They are dazzled audiences
        print(it!)
        Rock = 86
        print(it!)
        Tommy = 73
        print(it!)
        break
        print("Bring on the rock!")
        Else print("That ain't it, Chief")
        break```

![no-alignment]({{ '/picoCTF-2019/solution-files/forensics-warmup-1-solution.jpg' | absolute_url }})


Flag: ```picoCTF{UNSOLVED}```