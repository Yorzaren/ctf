---
title: "Mr-Worldwide"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - cryptography
---

Problem: A musician left us a message. What's it mean?

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/mr-worldwide.txt "Download file")

Solution: There are geo coordinates. Each coordinate represents a letter. 

```
(35.028309, 135.753082) = Kyoto, Japan
(46.469391, 30.740883) = Odesa, Ukraine
(39.758949, -84.191605) = Dayton, United States
(41.015137, 28.979530) = İstanbul, Turkey
(24.466667, 54.366669) = Abu Dhabi, United Arab Emirates
(3.140853, 101.693207) = Kuala Lumpur, Malaysia
_
(9.005401, 38.763611) = Addis Ababa, Ethiopia
(-3.989038, -79.203560) = Loja, Ecuador
(52.377956, 4.897070) = Amsterdam, Netherlands
(41.085651, -73.858467) = Sleepy Hollow, United States
(57.790001, -152.407227) = Kodiak, United States
(31.205753, 29.924526) = Alexandria Governorate, Egypt
```
Take the first letters ```KODIAK_ALASKA```


Flag: ```picoCTF{KODIAK_ALASKA}```