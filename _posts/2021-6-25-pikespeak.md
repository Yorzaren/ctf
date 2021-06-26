---
title: "PikesPeak"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Pay attention to those strings!

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/PikesPeak.jpg "Download file")

Solution: 

`strings -n 7 -t x PikesPeak.jpg | grep {`

Returns:

```
     18 CTFLEARN{PikesPeak}
     30 CTFLearn{Colorado}
     46 %ctflearn{MountainMountainMountain}
     6d #cTfLeArN{CTFMountainCTFmOUNTAIN}
     93 CTF{AsPEN.Vail}
     a7 CTFlearn{Gandalf}
     bd ctflearning{AUCKLAND}
     d7 ctfLEARN{MtDoom}
     eb 6ctflearninglearning{Mordor.TongariroAlpineCrossing}
    123 +CTFLEARN{MountGedePangrangoNationalPark}
    150 $ctflearncTfLeARN{MountKosciuszko}
   1b80 {r%681G
```

The flag follows: CTFlearn{}.

Flag: `CTFlearn{Gandalf}`