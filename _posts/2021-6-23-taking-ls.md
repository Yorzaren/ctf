---
title: "Taking LS"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - forensics
---

Just take the Ls. Check out this zip file and I be the flag will remain hidden. https://mega.nz/#!mCgBjZgB!_FtmAm8s_mpsHr7KWv8GYUzhbThNn0I8cHMBi4fJQp8

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/CTFlearn/problem-files/The_Flag.zip "Download file")

Solution: 

unzip the file: `unzip 'The Flag.zip'`

change directories into the flag folder: `cd 'The Flag'`

List all the files including the hidden ones: `ls -la`

`cd .ThePassword`

`cat ThePassword.txt`

Returns:
`Nice Job!  The Password is "Im The Flag".`

Using the password on the pdf. Pdf reads: `Here is the Flag: ABCTF{T3Rm1n4l_is_C00l}`

Flag: `ABCTF{T3Rm1n4l_is_C00l}`