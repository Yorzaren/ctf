---
title: "vault-door-6"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: This vault uses an XOR encryption scheme. The source code for this vault is here: VaultDoor6.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-6.java "Download file")

Solution: Java code 

```
byte[] myBytes = {
	0x3b, 0x65, 0x21, 0xa , 0x38, 0x0 , 0x36, 0x1d,
	0xa , 0x3d, 0x61, 0x27, 0x11, 0x66, 0x27, 0xa ,
	0x21, 0x1d, 0x61, 0x3b, 0xa , 0x2d, 0x65, 0x27,
	0xa , 0x66, 0x61, 0x6d, 0x61, 0x30, 0x37, 0x36,
};
for (int i=0; i<32; i++) {
	System.out.print(myBytes[i] ^ 0x55);
	System.out.print(" ");
}
```

Output:
```110 48 116 95 109 85 99 72 95 104 52 114 68 51 114 95 116 72 52 110 95 120 48 114 95 51 52 56 52 101 98 99```

Flag: ```picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_3484ebc}```