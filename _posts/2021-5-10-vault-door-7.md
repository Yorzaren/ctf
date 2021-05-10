---
title: "vault-door-7"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - reverse engineering
---

Problem: This vault uses bit shifts to convert a password string into an array of integers. Hurry, agent, we are running out of time to stop Dr. Evil's nefarious plans! The source code for this vault is here: VaultDoor7.java

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2019/problem-files/vault-door-7.java "Download file")

Solution: Convert the encrypted password from integer to binary. Split into 4 segments of length 8. Convert binary into hex and then hex into an ascii letter.

javascript:
```
var password = [1096770097,1952395366,1600270708,1601398833,1716808014,1734293603,959591523,842097204];
var binary_seg = [];
var hex_seg = [];
var decoded = [];
String.prototype.bin = function () {
	return parseInt(this, 2);
};
Number.prototype.bin = function () {
	var sign = (this < 0 ? "-" : "");
	var result = Math.abs(this).toString(2);
	while(result.length < 32) {
		result = "0" + result;
	}
	return sign + result;
}


function bin2hex(bin) {
	return parseInt(bin, 2).toString(16).toUpperCase();
}

function hex2a(hexx) {
	var hex = hexx.toString();//force conversion
	var str = '';
	for (var i = 0; (i < hex.length && hex.substr(i, 2) !== '00'); i += 2)
		str += String.fromCharCode(parseInt(hex.substr(i, 2), 16));
	return str;
}


for (i in password) {
	var og = password[i];
	var bin_n = og.bin();
	var bin_seg = bin_n.match(/.{1,8}/g);
	console.log(bin_seg);
	for (var j=0; j<4; j++) {
		var hex = bin2hex(bin_seg[j]);
		console.log(hex);
		hex_seg.push(hex);
	}
	console.log(hex_seg);
}

for (z in hex_seg) {
	decoded.push(hex2a(hex_seg[z]));
}
console.log(decoded.toString().replace(/,/g,' '));
```


Flag: ```picoCTF{A_b1t_0f_b1t_sh1fTiNg_8c924c21b4}```