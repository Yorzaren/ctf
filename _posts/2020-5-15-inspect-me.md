---
title: "Inspect Me"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
---

Problem: Inpect this code! [http://2018shell.picoctf.com:53213](http://2018shell.picoctf.com:53213) (link)

Solution: Look at the websites html code. Near the bottem there's ```<!-- I learned HTML! Here's part 1/3 of the flag: picoCTF{ur_4_real_1nspe -->```
Next look at the css and js files.
CSS file:
```/* I learned CSS! Here's part 2/3 of the flag: ct0r_g4dget_402b0bd3} */```
JS file:
```/* I learned JavaScript! Here's part 3/3 of the flag:  */```

And put all the parts together for the flag.

Flag: ```picoCTF{ur_4_real_1nspect0r_g4dget_402b0bd3}```