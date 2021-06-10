---
title: "Javascript - Authentication"
categories:
  - Root Me
tags:
  - Root Me
  - web-client
---

Statement:
None

Solution: 

Exploring the page's source you see

```
<html>
<head>
<script type="text/javascript" src="login.js"></script>
</head>
<body><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>
    <fieldset style="margin-top: 10px; padding: 10px;" width="60%">
	<legend><b>Login</b></legend><br/>
	<form name="login" method="POST" action="">
	    Username : <input name="pseudo" /><br/>
	    Password : <input type="password" name="password" /></br></br>
	    <input onclick="Login()" type="button" value="login" name="button" />
	</form>
    </fieldset>
</body>
</html>
```

The login.js
```
/* <![CDATA[ */

function Login(){
	var pseudo=document.login.pseudo.value;
	var username=pseudo.toLowerCase();
	var password=document.login.password.value;
	password=password.toLowerCase();
	if (pseudo=="4dm1n" && password=="sh.org") {
	    alert("Password accepté, vous pouvez valider le challenge avec ce mot de passe.\nYou an validate the challenge using this password.");
	} else { 
	    alert("Mauvais mot de passe / wrong password"); 
	}
}
/* ]]> */ 
```

Which gives:

user: 4dm1n
password: sh.org

When plugged in gives us the alert: Password accepté, vous pouvez valider le challenge avec ce mot de passe.\nYou an validate the challenge using this password.

Which refers to `sh.org`

Validation: `sh.org`