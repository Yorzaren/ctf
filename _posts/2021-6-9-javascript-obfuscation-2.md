---
title: "Javascript - Obfuscation 2"
categories:
  - Root Me
tags:
  - Root Me
  - web-client
---

Statement:
None.

Solution: 

View page source:

```
<html>

<head>
	<title>Obfuscation JS</title>
<!-- 
Obfuscation 
.Niveau : Facile 
.By Hel0ck
.The mission : 
	Retrouver le password contenu dans la var pass.
	You need my help ? IRC : irc.root-me.org #root-me
-->
<script type="text/javascript">
	var pass = unescape("unescape%28%22String.fromCharCode%2528104%252C68%252C117%252C102%252C106%252C100%252C107%252C105%252C49%252C53%252C54%2529%22%29");
</script>
</head>

</html>
```

Unescape the string twice and then you have `String.fromCharCode(104,68,117,102,106,100,107,105,49,53,54)`

Which becomes `hDufjdki156`

Validation: `hDufjdki156`