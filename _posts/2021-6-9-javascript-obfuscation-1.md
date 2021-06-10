---
title: "Javascript - Obfuscation 1"
categories:
  - Root Me
tags:
  - Root Me
  - web-client
---

Statement:
None.

Solution: 

View the page source:

```
<html>
    <head>
        <title>Obfuscation JS</title>

          <script type="text/javascript">
              /* <![CDATA[ */

              pass = '%63%70%61%73%62%69%65%6e%64%75%72%70%61%73%73%77%6f%72%64';
              h = window.prompt('Entrez le mot de passe / Enter password');
              if(h == unescape(pass)) {
                  alert('Password accepté, vous pouvez valider le challenge avec ce mot de passe.\nYou an validate the challenge using this pass.');
              } else {
                  alert('Mauvais mot de passe / wrong password');
              }

              /* ]]> */
          </script>
    </head>
   <body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>
    </body>
</html>

```

You can see this is the password `%63%70%61%73%62%69%65%6e%64%75%72%70%61%73%73%77%6f%72%64` but you need to decode it from url encoding.

A decoder: [https://meyerweb.com/eric/tools/dencoder/](https://meyerweb.com/eric/tools/dencoder/)

which gives you this `cpasbiendurpassword`

Validation: `cpasbiendurpassword`