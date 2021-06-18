---
title: "Client side validation is so secure?"
categories:
  - RingZer0-CTF
tags:
  - RingZer0-CTF
  - Javascript
---

Solution: 

Reading the page source code:
```html
<h4>Client side validation is so secure?
</h4>
<hr />

		<div class="challenge-wrapper">
			<form action="" method="post">
				<label>Username</label>
				<input class="form-control" type="text" name="username" id="cuser" placeholder="Username" />
				<label>Password</label>
				<input class="form-control" type="password" name="password" id="cpass" placeholder="Password" />
				<input type="submit" style="margin-top: 12px;" value="Login" class="c_submit form-control btn btn-success" />
			</form>
		</div>
		<div id="cresponse">
		</div>
		<script>
			// Look's like weak JavaScript auth script :)
			$(".c_submit").click(function(event) {
				event.preventDefault()
				var u = $("#cuser").val();
				var p = $("#cpass").val();
				if(u == "admin" && p == String.fromCharCode(74,97,118,97,83,99,114,105,112,116,73,115,83,101,99,117,114,101)) {
				    if(document.location.href.indexOf("?p=") == -1) {   
				        document.location = document.location.href + "?p=" + p;
				    }
				} else {
				    $("#cresponse").html("<div class='alert alert-danger'>Wrong password sorry.</div>");
				}
			});
		</script>
		
<hr />
```

You decode the password from the `String.fromCharCode(74,97,118,97,83,99,114,105,112,116,73,115,83,101,99,117,114,101)` which is `JavaScriptIsSecure`.

Username is: `admin`.

Submit it to the form to get the flag.

Flag: ```FLAG-66Jq5u688he0y46564481WRh```