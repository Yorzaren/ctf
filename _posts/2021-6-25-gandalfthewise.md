---
title: "GandalfTheWise"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Extract the flag from the Gandalf.jpg file. You may need to write a quick script to solve this.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/Gandalf.jpg "Download file")


Solution: 

`exiftool Gandalf.jpg`

Base64

`Q1RGbGVhcm57eG9yX2lzX3lvdXJfZnJpZW5kfQo=.` = CTFlearn{xor_is_your_friend}

Not the flag.


```
Q1RGbGVhcm57eG9yX2lzX3lvdXJfZnJpZW5kfQo=
xD6kfO2UrE5SnLQ6WgESK4kvD/Y/rDJPXNU45k/p
h2riEIj13iAp29VUPmB+TadtZppdw3AuO7JRiDyU
```

script.py

```python		
import base64

string1 = "xD6kfO2UrE5SnLQ6WgESK4kvD/Y/rDJPXNU45k/p"
string2 = "h2riEIj13iAp29VUPmB+TadtZppdw3AuO7JRiDyU"

c1 = base64.b64decode(string1)
c2 = base64.b64decode(string2)

c = []
l = len(c1)

i = 0
while i < l:
  c.append(chr(c1[i] ^ c2[i]))
  i += 1

print("".join(c))
```	

Flag: `CTFlearn{Gandalf.BilboBaggins}`