---
title: "Network Attacks"
categories:
  - CRYPTOHACK
tags:
  - CRYPTOHACK
  - introduction
---

Several of the challenges are dynamic and require you to talk to our challenge servers over the network. This allows you to perform man-in-the-middle attacks on people trying to communicate, or directly attack a vulnerable service. To keep things consistent, our interactive servers always send and receive JSON objects.

Python makes such network communication easy with the `telnetlib` module. Conveniently, it's part of Python's standard library, so let's use it for now.

For this challenge, connect to `socket.cryptohack.org` on port `11112`. Send a JSON object with the key `buy` and value `flag`.

The example script below contains the beginnings of a solution for you to modify, and you can reuse it for later challenges.

Connect at `nc socket.cryptohack.org 11112`

[telnetlib.py](https://github.com/Yorzaren/ctf/raw/master/CRYPTOHACK/telnetlib.py)

Solution: 

Download the script they give you and modify the request section.

```
request = {
    "buy": "flag"
}
```

Then run it using python.

```
Welcome to netcat's flag shop!

What would you like to buy?

I only speak JSON, I hope that's ok.



{u'flag': u'crypto{sh0pp1ng_f0r_fl4g5}'}
```

Flag: ```crypto{sh0pp1ng_f0r_fl4g5}```