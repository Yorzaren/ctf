---
title: "Gobustme 👻"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - web
---

Some ghosts made this site 👻, it's a little spooky but theres a bunch of stuff hidden around.

[gobustme.ctflearn.com](gobustme.ctflearn.com)

Solution: 

Theres a resource on the page linking an article on gobuster and another page to a wordlist.

Grab a copy  of the wordlist.

`wget https://raw.githubusercontent.com/v0re/dirb/master/wordlists/common.txt`

Run gobuster on the website using the downloaded wordlist.

`gobuster dir -u https://gobustme.ctflearn.com/ -w common.txt`

It returns: 
```
/call (Status: 301)
/carpet (Status: 301)
/flag (Status: 301)
/hide (Status: 301)
/index.html (Status: 200)
/sex (Status: 301)
/shadow (Status: 301)
/skin (Status: 301)
```

Checking flag it isnt there. Checking the hide you find the flag. `It was well hidden isn't it? CTFlearn{gh0sbu5t3rs_4ever} 👻`

Flag: `CTFlearn{gh0sbu5t3rs_4ever}`