---
title: "abandoned place"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

PLACEHOLDER

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/abondoned_street_challenge2.jpg "Download file")


Solution: 

It wants us to check the dimensions 

`exiftool abondoned_street_challenge2.jpg`

```
Image Width                     : 2016
Image Height                    : 900
```

2016 = 07E0
900 = 0384

Using a hex editor flip those dimensions.

File: [Corrected_image](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/abandoned-street-solved.jpg "Download file")

Flag: `urban_exploration`