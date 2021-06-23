---
title: "POST Practice"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - web
---

This website requires authentication, via POST. However, it seems as if someone has defaced our site. Maybe there is still some way to authenticate? http://165.227.106.113/post.php

Solution: 

You need to send a POST request.

The website also has the username and password you need to send in and html comment on the page.

`username: admin | password: 71urlkufpsdnlkadsf`

`curl -d "username=admin&password=71urlkufpsdnlkadsf" -X POST http://165.227.106.113/post.php`

Returns: `<h1>flag{p0st_d4t4_4ll_d4y}</h1>`

Flag: `flag{p0st_d4t4_4ll_d4y}`