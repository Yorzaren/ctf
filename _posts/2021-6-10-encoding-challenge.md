---
title: "Encoding Challenge"
categories:
  - CRYPTOHACK
tags:
  - CRYPTOHACK
  - general
  - encoding
---

Now you've got the hang of the various encodings you'll be encountering, let's have a look at automating it.

Can you pass all 100 levels to get the flag?

The 13377.py file attached below is the source code for what's running on the server. The pwntools_example.py file provides the start of a solution using the incredibly convenient pwntools library. which you can use if you like. pwntools however is incompatible with Windows, so telnetlib_example.py is also provided.

For more information about connecting to interactive challenges, see the FAQ. Feel free to skip ahead to the cryptography if you aren't in the mood for a coding challenge!

Connect at `nc socket.cryptohack.org 13377`

[13377.py](https://github.com/Yorzaren/ctf/raw/master/CRYPTOHACK/13377_encoding_challenge.py)

[pwntools_example.py](https://github.com/Yorzaren/ctf/raw/master/CRYPTOHACK/pwntools_example_encoding_challenge.py)

[telnetlib_example.py](https://github.com/Yorzaren/ctf/raw/master/CRYPTOHACK/telnetlib_example_encoding_challenge.py)

Solution: 

Using the pwntools_example to build the script.

```
from pwn import * # pip install pwntools
import json
from Crypto.Util.number import bytes_to_long, long_to_bytes
import base64
import codecs
import array


r = remote('socket.cryptohack.org', 13377, level = 'debug')

def json_recv():
	line = r.recvline()
	return json.loads(line.decode())

def json_send(hsh):
	request = json.dumps(hsh).encode()
	r.sendline(request)

for i in range(0,101):
	received = json_recv()

	if "flag" in received:
		print(received)
		break

	print("\n\n")
	print("Received type: ")
	print(received["type"])
	print("Received encoded value: ")
	print(received["encoded"])

	encoding = received["type"]
	word = received["encoded"]

	if encoding == "base64":#PASSED
		decoded = base64.b64decode(word).decode('utf-8')
	elif encoding == "hex": #PASSED
		decode_hex = codecs.getdecoder("hex_codec")
		decoded = decode_hex(word)[0].decode('utf-8')
	elif encoding == "rot13":#PASSED
		decoded = codecs.encode(word, 'rot_13')
	elif encoding == "bigint":
		# Spent way too long troubleshooting this
		# Its a string so to make it work you have
		# to convert it.
		decoded = long_to_bytes(int(word,16)).decode('utf-8')
	elif encoding == "utf-8": #PASSED
		decoded = array.array('b', word).tobytes().decode('utf-8')

	print("DECODED: "+decoded)

	to_send = {
		"decoded": decoded
	}
	json_send(to_send)
```

Flag: `crypto{3nc0d3_d3c0d3_3nc0d3}`