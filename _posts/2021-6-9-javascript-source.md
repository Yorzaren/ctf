---
title: "Javascript - Source"
categories:
  - Root Me
tags:
  - Root Me
  - web-client
---

Statement:
None

Solution: 
Opening the page you get an alert type something and you'll see that the password is wrong. 

Open the page source

```html
<html>
    <head>
	<script type="text/javascript">
	/* <![CDATA[ */
	    function login(){
		pass=prompt("Entrez le mot de passe / Enter password");
		if ( pass == "123456azerty" ) {
		    alert("Mot de passe accepté, vous pouvez valider le challenge avec ce mot de passe.\nYou can validate the challenge using this password.");  }
		else {
		    alert("Mauvais mot de passe / wrong password !");
		}
	    }
	/* ]]> */
	</script>
    </head>
   <body onload="login();"><link rel='stylesheet' property='stylesheet' id='s' type='text/css' href='/template/s.css' media='all' /><iframe id='iframe' src='https://www.root-me.org/?page=externe_header'></iframe>

    </body>
</html>
```

And the password is `123456azerty`

Validation: `123456azerty`