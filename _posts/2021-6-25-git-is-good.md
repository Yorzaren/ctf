---
title: "Git Is Good"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

The flag used to be there. But then I redacted it. Good Luck. https://mega.nz/#!3CwDFZpJ!Jjr55hfJQJ5-jspnyrnVtqBkMHGJrd6Nn_QqM7iXEuc

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/gitIsGood.zip "Download file")

Solution: 

Extract the zip file.

cd into the extracted folder and then run git to review the history.

`git log -p flag.txt`

Flag: `flag{protect_your_git}`