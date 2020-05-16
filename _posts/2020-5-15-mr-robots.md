---
title: "Mr. Robots"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - web exploitation
---

Problem: Do you see the same things I see? The glimpses of the flag hidden away? [http://2018shell.picoctf.com:10157](http://2018shell.picoctf.com:10157) (link)

Solution: 

Go to the site and there's nothing there.

![no-alignment]({{ '/picoCTF-2018/solution-files/mr-robots-img-1.jpg' | absolute_url }})

There's nothing in the source code, either.

BUT, The title is a hint. Let's visit the ```robots.txt``` at http://2018shell.picoctf.com:10157/robots.txt

![no-alignment]({{ '/picoCTF-2018/solution-files/mr-robots-img-2.jpg' | absolute_url }})

Then we see ```Disallow: /143ce.html```. After going there we get the flag.

![no-alignment]({{ '/picoCTF-2018/solution-files/mr-robots-img-3.jpg' | absolute_url }})

Flag: ```picoCTF{th3_w0rld_1s_4_danger0us_pl4c3_3lli0t_143ce}```