---
title: "Is hashing more secure?"
categories:
  - RingZer0-CTF
tags:
  - RingZer0-CTF
  - Javascript
---

Solution: 

```html
<h4>
Is hashing more secure?
</h4>

<hr />

		<div class="challenge-wrapper">
			<form action="" method="post">
				<label>Password</label>
				<input type="password" class="form-control" name="password" id="cpass" placeholder="Password" />
				<input type="submit" style="margin-top: 12px;" value="Login" class="c_submit form-control btn btn-success" />
			</form>
		</div>
		<div id="cresponse">
		</div>
		<script type="text/javascript" src="/script/sha1.js"></script>
		<script>
			// Look's like weak JavaScript auth script :)
			$(".c_submit").click(function(event) {
				event.preventDefault();
				var p = $("#cpass").val();
				if(Sha1.hash(p) == "b89356ff6151527e89c4f3e3d30c8e6586c63962") {
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

The password is encypted using Sha1 which you can use an online decypter getting `adminz`.

Flag: ```FLAG-bXNsYg9tLCaIX6h1UiQMmMYB```