---
title: "Don't Bump Your Head(er)"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - web
---

Try to bypass my security measure on this site! http://165.227.106.113/header.php

Solution: 

The site tell you the user agent is wrong when you go there and in the html comment you see `Sup3rS3cr3tAg3nt`

So you can either use the webtools to change the user agent or you can use curl

`curl -A "user-agent-name-here" [URL]`

`curl -A "Sup3rS3cr3tAg3nt" http://165.227.106.113/header.php`

Response: Sorry, it seems as if you did not just come from the site, "awesomesauce.com".

Change the referer.

`curl -A "Sup3rS3cr3tAg3nt" http://165.227.106.113/header.php -H "Referer: awesomesauce.com"`

And success: Here is your flag: flag{did_this_m3ss_with_y0ur_h34d}

Flag: `flag{did_this_m3ss_with_y0ur_h34d}`