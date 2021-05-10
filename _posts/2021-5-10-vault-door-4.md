---
title: "vault-door-4"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: This vault uses ASCII encoding for the password. The source code for this vault is here: VaultDoor4.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-4.java "Download file")

Solution: 

Find the bytes
```
106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
0142, 0131, 0164, 063 , 0163, 0137, 0142, 071 ,
'e' , '9' , '2' , 'f' , '7' , '6' , 'a' , 'c' ,
```
Convert them into ascii. Its a mix of hex, octal, and decimal. https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html

line 1 is decimal = ```jU5t_4_b```

line 2 is hex = ```UnCh_0f_```

line 3 is octal = ```bYt3s_b9```

line 4 is itself = ```e92f76ac```

Flag: ```picoCTF{jU5t_4_bUnCh_0f_bYt3s_b9e92f76ac}```