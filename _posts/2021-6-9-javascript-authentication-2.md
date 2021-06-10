---
title: "Javascript - Authentication 2"
categories:
  - Root Me
tags:
  - Root Me
  - web-client
---

Statement:
None

Solution: 

View the page source:

```

<html>
    <head>
	<title>JS Authentication</title>
	<script language="JavaScript" src="login.js"></script>
    </head>
   <body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>
	<div id=EchoTopic>
	<p>Authentication</p>
	<p><input type="button" value="login" onclick="connexion();"></p>
	<br/><br/>
	<a href="javascript:window.close();">Close Window</a>
	</div>
    </body>
</html>

```

This is login.js

```
function connexion(){
    var username = prompt("Username :", "");
    var password = prompt("Password :", "");
    var TheLists = ["GOD:HIDDEN"];
    for (i = 0; i < TheLists.length; i++)
    {
        if (TheLists[i].indexOf(username) == 0)
        {
            var TheSplit = TheLists[i].split(":");
            var TheUsername = TheSplit[0];
            var ThePassword = TheSplit[1];
            if (username == TheUsername && password == ThePassword)
            {
                alert("Vous pouvez utiliser ce mot de passe pour valider ce challenge (en majuscules) / You can use this password to validate this challenge (uppercase)");
            }
        }
        else
        {
            alert("Nope, you're a naughty hacker.")
        }
    }
}
```

User: GOD
Password: HIDDEN

Validation: `HIDDEN`