---
title: "PDF by fdpumyp"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Hi, just as we talked during a break, you have this file here and check if something is wrong with it. That's the only thing we found strange with this suspect, I hope there will be a password for his external drive

Bye

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/dontopen.pdf "Download file")

Solution: 

`cat dontopen.pdf`

```
== SECRET DATA DONT LOOK AT THIS ==

external:Q1RGbGVhcm57KV8xbDB3M3kwVW0wMG15MTIzfQ==
pin:1234
password:MTIzMVdST05HOWlzamRuUEFTU1dPUkQ=

endstream
endobj

xref
8 1
0000149877 00000 n 
13 1
0000150079 00000 n 

trailer
<</Size 14/Root 8 0 R/Info 1 0 R/Prev 149539>>
```

Converted: `Q1RGbGVhcm57KV8xbDB3M3kwVW0wMG15MTIzfQ==` = `CTFlearn{)_1l0w3y0Um00my123}`

Which is apparently the flag after testing it. Not sure what the password or pin is for...

Flag: `CTFlearn{)_1l0w3y0Um00my123}`