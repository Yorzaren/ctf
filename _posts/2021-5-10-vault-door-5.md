---
title: "vault-door-5"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: VaultDoor5.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-5.java "Download file")

Solution: 
```
public boolean checkPassword(String password) {
	String urlEncoded = urlEncode(password.getBytes());
	String base64Encoded = base64Encode(urlEncoded.getBytes());
	String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
					+ "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
					+ "JTM0JTVmJTYzJTMxJTM0JTYzJTYzJTY1JTMxJTMx";
	return base64Encoded.equals(expected);
}
```
Convert from base64 = ```%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%63%31%34%63%63%65%31%31```

Convert from urlEncode = ```c0nv3rt1ng_fr0m_ba5e_64_c14cce11```

Flag: ```picoCTF{c0nv3rt1ng_fr0m_ba5e_64_c14cce11}```