---
title: "Who are you?"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - web exploitation
---

Problem: Let me in. Let me iiiiiiinnnnnnnnnnnnnnnnnnnn http://mercury.picoctf.net:36622/

Solution: 

https://everything.curl.dev/http/requests

Using https://reqbin.com/req/c-ea0d5rlb/curl-add-header

Going to the page it tell you, you need to use the PicoBrowser.

```curl -A "PicoBrowser" http://mercury.picoctf.net:36622/```

After setting the user agent to PicoBrowser is says "I don't trust users visiting from another site."

```curl -A "PicoBrowser" -H "Referer: http://mercury.picoctf.net:36622/" http://mercury.picoctf.net:36622/```

"Sorry, this site only worked in 2018."

```
curl http://mercury.picoctf.net:36622/
	-H "user-agent: PicoBrowser"
	-H "Referer: http://mercury.picoctf.net:36622/"
    -H "Date: Sun, 18 Mar 2018"
```

"I don't trust users who can be tracked."

```
curl http://mercury.picoctf.net:36622/
	-H "user-agent: PicoBrowser"
	-H "Referer: http://mercury.picoctf.net:36622/"
    -H "Date: Sun, 18 Mar 2018"
    -H "DNT: 1"
```

"This website is only for people from Sweden"

```
curl http://mercury.picoctf.net:36622/
	-H "user-agent: PicoBrowser"
	-H "Referer: http://mercury.picoctf.net:36622/"
    -H "Date: Sun, 18 Mar 2018"
    -H "DNT: 1"
    -H "X-Forwarded-For: 2.16.69.255"
```

"You're in Sweden but you don't speak Swedish?"

```
curl http://mercury.picoctf.net:36622/
	-H "user-agent: PicoBrowser"
	-H "Referer: http://mercury.picoctf.net:36622/"
    -H "Date: Sun, 18 Mar 2018"
    -H "DNT: 1"
    -H "X-Forwarded-For: 2.16.69.255"
    -H "Accept-Language: SV"
```

![no-alignment]({{ '/picoCTF-2021/solution-files/who-are-you.jpg' | absolute_url }})


Flag: ```picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_0da16bb2}```