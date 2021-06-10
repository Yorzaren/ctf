---
title: "Bytes and Big Integers"
categories:
  - CRYPTOHACK
tags:
  - CRYPTOHACK
  - general
  - encoding
---

Cryptosystems like RSA works on numbers, but messages are made up of characters. How should we convert our messages into numbers so that mathematical operations can be applied?

The most common way is to take the ordinal bytes of the message, convert them into hexadecimal, and concatenate. This can be interpreted as a base-16 number, and also represented in base-10.

To illustrate:
```
message: HELLO
ascii bytes: [72, 69, 76, 76, 79]
hex bytes: [0x48, 0x45, 0x4c, 0x4c, 0x4f]
base-16: 0x48454c4c4f
base-10: 310400273487
```
Python's PyCryptodome library implements this with the methods `Crypto.Util.number.bytes_to_long` and `Crypto.Util.number.long_to_bytes`.

Convert the following integer back into a message:

`11515195063862318899931685488813747395775516287289682636499965282714637259206269`

Solution: 

Make a script `convert.py`

```
from Crypto.Util.number import bytes_to_long
from Crypto.Util.number import long_to_bytes

num = 1151519506386231889993168548881374739577551628728968263649996528271463725>

ans = long_to_bytes(num)

print(ans)
```

run it `python3 convert.py`

Flag: `crypto{3nc0d1n6_4ll_7h3_w4y_d0wn}`