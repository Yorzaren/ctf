---
title: "vault-door-3"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: This vault uses for-loops and byte arrays. The source code for this vault is here: VaultDoor3.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-3.java "Download file")

Solution: From the file.

```
public boolean checkPassword(String password) {
	if (password.length() != 32) {
		return false;
	}
	char[] buffer = new char[32];
	int i;
	for (i=0; i<8; i++) {
		buffer[i] = password.charAt(i);
	}
	for (; i<16; i++) {
		buffer[i] = password.charAt(23-i);
	}
	for (; i<32; i+=2) {
		buffer[i] = password.charAt(46-i);
	}
	for (i=31; i>=17; i-=2) {
		buffer[i] = password.charAt(i);
	}
	String s = new String(buffer);
	return s.equals("jU5t_a_sna_3lpm1dg347_u_4_mfr54b");
}
```
Easier to convert to js.
```
password = "jU5t_a_sna_3lpm1dg347_u_4_mfr54b";
var buffer = Array(32);
var i;
for (i=0; i<8; i++) {
	buffer[i] = password.charAt(i);
}
for (; i<16; i++) {
	buffer[i] = password.charAt(23-i);
}
for (; i<32; i+=2) {
	buffer[i] = password.charAt(46-i);
}
for (i=31; i>=17; i-=2) {
	buffer[i] = password.charAt(i);
}
console.log(buffer.toString().replace(/,/g, ''));

```


Flag: ```picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_7f35db}```