---
title: "Simple Steganography"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Think the flag is somewhere in there. Would you help me find it? hint-" Steghide Might be Helpfull"

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/Minions1.jpeg "Download file")

Solution: 

To extract from steghide we need a password.

`exiftool Minions1.jpeg`

```
Keywords                        : myadmin
```

Looks like it could be it.

`steghide --extract -sf Minions1.jpeg -p myadmin`

File extracted.

`cat raw.txt`

```
AEMAVABGAGwAZQBhAHIAbgB7AHQAaABpAHMAXwBpAHMAXwBmAHUAbgB9
```

`.C.T.F.l.e.a.r.n.{.t.h.i.s._.i.s._.f.u.n.}`

Strip the extra `.`s.

Flag: `CTFlearn{this_is_fun}`