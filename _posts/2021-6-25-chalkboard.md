---
title: "Chalkboard"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Solve the equations embedded in the jpeg to find the flag. Solve this problem before solving my Scope challenge which is worth 100 points.

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/math.jpg "Download file")

Solution: 

```
Comment: The flag for this challenge is of the form:..CTFlearn{I_Like_Math_x_y}..where x and y are the solution to these equations:..3x + 5y = 31..7x + 9y = 59...
```

Solve them: 3x + 5y = 31 and 7x + 9y = 59

`x=2, y=5`

Plug it in: CTFlearn{I_Like_Math_2_5}

Flag: `CTFlearn{I_Like_Math_2_5}`