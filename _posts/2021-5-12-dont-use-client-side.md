---
title: "dont-use-client-side"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - web exploitation
---

Problem: Can you break into this super secure portal? https://2019shell1.picoctf.com/problem/45147/ (link) or http://2019shell1.picoctf.com:45147

Solution: Going to that page you are greeted with the most violently blue login page ever. But as the problem implies the page uses client side verification. Lets look at the page source.

```

<html>
<head>
<title>Secure Login Portal</title>
</head>
<body bgcolor=blue>
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split) == 'pico') {
      if (checkpass.substring(split*6, split*7) == 'a60f') {
        if (checkpass.substring(split, split*2) == 'CTF{') {
         if (checkpass.substring(split*4, split*5) == 'ts_p') {
          if (checkpass.substring(split*3, split*4) == 'lien') {
            if (checkpass.substring(split*5, split*6) == 'lz_4') {
              if (checkpass.substring(split*2, split*3) == 'no_c') {
                if (checkpass.substring(split*7, split*8) == '3}') {
                  alert("Password Verified")
                  }
                }
              }
      
            }
          }
        }
      }
    }
    else {
      alert("Incorrect password");
    }
    
  }
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:yellow">
<div style="text-align:center">
<p>This is the secure login portal</p>
<p>Enter valid credentials to proceed</p>
<form action="index.html" method="post">
<input type="password" id="pass" size="8" />
<br/>
<input type="submit" value="verify" onclick="verify(); return false;" />
</form>
</div>
</div>
</body>
</html>
```

And there's the flag, after a bit of reconstruction from the split. ```picoCTF{no_clients_plz_4a60f3}```

Flag: ```picoCTF{no_clients_plz_4a60f3}```