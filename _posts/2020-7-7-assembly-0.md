---
title: "assembly-0"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - reversing
---

Problem: What does `asm0(0xaa,0xf2)` return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. Source located in the directory at `/problems/assembly-0_2_485b2d48345b19addbeb06a36aabdc74`.



File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2018/problem-files/intro_asm_rev.S "Download file")

Solution: 

```.intel_syntax noprefix
.bits 32
	
.global asm0

asm0:
	push ebp
	mov	ebp,esp
	mov	eax,DWORD PTR [ebp+0x8]
	mov	ebx,DWORD PTR [ebp+0xc]
	mov	eax,ebx
	mov	esp,ebp
	pop	ebp	
	ret```

`asm0` is a function so calling `asm0(0xaa,0xf2)` makes `0xaa` and `0xf2` arguments.


```
asm0:
	push ebp
	mov	ebp,esp	; ebp = esp
	mov	eax,DWORD PTR [ebp+0x8]	; eax = arg1, so in this case its 0xaa
	mov	ebx,DWORD PTR [ebp+0xc]	; ebx = arg2, so in this case its 0xf2
	mov	eax,ebx	; eax = ebx, so eax now is the value 0xf2
	mov	esp,ebp	; esp = ebp
	pop	ebp	
	ret	; assembly code returns eax, in this case its 0xf2
```

Flag: ```0xf2```