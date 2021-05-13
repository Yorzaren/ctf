---
title: "Client-side-again"
categories:
  - picoCTF-2019
tags:
  - picoCTF
  - picoCTF-2019
  - web exploitation
---

Problem: Can you break into this super secure portal? https://2019shell1.picoctf.com/problem/21886/ (link) or http://2019shell1.picoctf.com:21886

Solution: The page.
```
<html>
<head>
<title>Secure Login Portal V2.0</title>
</head>
<body background="barbed_wire.jpeg" >
<!-- standard MD5 implementation -->
<script type="text/javascript" src="md5.js"></script>

<script type="text/javascript">
  var _0x5a46=['9f266}','_again_1','this','Password\x20Verified','Incorrect\x20password','getElementById','value','substring','picoCTF{','not_this'];(function(_0x4bd822,_0x2bd6f7){var _0xb4bdb3=function(_0x1d68f6){while(--_0x1d68f6){_0x4bd822['push'](_0x4bd822['shift']());}};_0xb4bdb3(++_0x2bd6f7);}(_0x5a46,0x1b3));var _0x4b5b=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x5a46[_0x2d8f05];return _0x4d74cb;};function verify(){checkpass=document[_0x4b5b('0x0')]('pass')[_0x4b5b('0x1')];split=0x4;if(checkpass[_0x4b5b('0x2')](0x0,split*0x2)==_0x4b5b('0x3')){if(checkpass[_0x4b5b('0x2')](0x7,0x9)=='{n'){if(checkpass[_0x4b5b('0x2')](split*0x2,split*0x2*0x2)==_0x4b5b('0x4')){if(checkpass[_0x4b5b('0x2')](0x3,0x6)=='oCT'){if(checkpass[_0x4b5b('0x2')](split*0x3*0x2,split*0x4*0x2)==_0x4b5b('0x5')){if(checkpass['substring'](0x6,0xb)=='F{not'){if(checkpass[_0x4b5b('0x2')](split*0x2*0x2,split*0x3*0x2)==_0x4b5b('0x6')){if(checkpass[_0x4b5b('0x2')](0xc,0x10)==_0x4b5b('0x7')){alert(_0x4b5b('0x8'));}}}}}}}}else{alert(_0x4b5b('0x9'));}}
</script>
<div style="position:relative; padding:5px;top:50px; left:38%; width:350px; height:140px; background-color:gray">
<div style="text-align:center">
<p>New and Improved Login</p>

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

This time the javascript has been obfuscated. I used https://www.dcode.fr/javascript-unobfuscator to get the following.

```
'use strict';
/* The array is _0x5a46 */
var _0x5a46 = ["9f266}", "_again_1", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
/* This function shifts the array around using the argument of array and an number 345 */
(function(data, i) {
    var validateGroupedContexts = function fn(selected_image) {
        for (; --selected_image;) {
            data["push"](data["shift"]());
        }
    };
    validateGroupedContexts(++i);
})(_0x5a46, 435);

/* This part just returns the array index of whatever. opt_target isnt even used. */
var _0x4b5b = function PocketDropEvent(ballNumber, opt_target) {
    ballNumber = ballNumber - 0;
    var ball = _0x5a46[ballNumber];
    return ball;
};

/* The main everything of the program */
function verify() {
    checkpass = document[_0x4b5b("0x0")]("pass")[_0x4b5b("0x1")];
    split = 4;
    if (checkpass[_0x4b5b("0x2")](0, split * 2) == _0x4b5b("0x3")) {
        if (checkpass[_0x4b5b("0x2")](7, 9) == "{n") {
            if (checkpass[_0x4b5b("0x2")](split * 2, split * 2 * 2) == _0x4b5b("0x4")) {
                if (checkpass[_0x4b5b("0x2")](3, 6) == "oCT") {
                    if (checkpass[_0x4b5b("0x2")](split * 3 * 2, split * 4 * 2) == _0x4b5b("0x5")) {
                        if (checkpass["substring"](6, 11) == "F{not") {
                            if (checkpass[_0x4b5b("0x2")](split * 2 * 2, split * 3 * 2) == _0x4b5b("0x6")) {
                                if (checkpass[_0x4b5b("0x2")](12, 16) == _0x4b5b("0x7")) {
                                    alert(_0x4b5b("0x8"));
                                }
                            }
                        }
                    }
                }
            }
        }
    } else {
        alert(_0x4b5b("0x9"));
    }
};
```

Lets try and figure out whats happening. I added some comments to the code recovered and cleaned. 
```
/* The data from _0x5a46 */
var data  = ["9f266}", "_again_1", "this", "Password Verified", "Incorrect password", "getElementById", "value", "substring", "picoCTF{", "not_this"];
/* from the array shifter function */
var i = 345;
// And the rest of it
var validateGroupedContexts = function fn(selected_image) {
        for (; --selected_image;) {
            data["push"](data["shift"]());
        }
    };
    validateGroupedContexts(++i);
console.log("New arrangement of data:");
console.log(data);
```

The new arrangement of the data array is:
```
0: "getElementById"
1: "value"
2: "substring"
3: "picoCTF{"
4: "not_this"
5: "9f266}"
6: "_again_1"
7: "this"
8: "Password Verified"
9: "Incorrect password"
```
Now just to subsitute ```_0x4b5b``` is ```data```. And the rest of it is 

```
var data = ["getElementById", "value", "substring", "picoCTF{", "not_this", "9f266}", "_again_1", "this", "Password Verified", "Incorrect password"];
function verify() {
    checkpass = document[data("0x0")]("pass")[data("0x1")];
    split = 4;
    if (checkpass[data("0x2")](0, split * 2) == data("0x3")) {
        if (checkpass[data("0x2")](7, 9) == "{n") {
            if (checkpass[data("0x2")](split * 2, split * 2 * 2) == data("0x4")) {
                if (checkpass[data("0x2")](3, 6) == "oCT") {
                    if (checkpass[data("0x2")](split * 3 * 2, split * 4 * 2) == data("0x5")) {
                        if (checkpass["substring"](6, 11) == "F{not") {
                            if (checkpass[data("0x2")](split * 2 * 2, split * 3 * 2) == data("0x6")) {
                                if (checkpass[data("0x2")](12, 16) == data("0x7")) {
                                    alert(data("0x8"));
                                }
                            }
                        }
                    }
                }
            }
        }
    } else {
        alert(data("0x9"));
    }
};
```

Putting it all together. 
```
var data = ["getElementById", "value", "substring", "picoCTF{", "not_this", "9f266}", "_again_1", "this", "Password Verified", "Incorrect password"];
function verify() {
    checkpass = document.getElementById("pass").value;
    split = 4;
    if (checkpass.substring(0, split * 2) == "picoCTF{") {
        if (checkpass.substring(7, 9) == "{n") {
            if (checkpass.substring(split * 2, split * 2 * 2) == not_this) {
                if (checkpass.substring(3, 6) == "oCT") {
                    if (checkpass.substring(split * 3 * 2, split * 4 * 2) == 9f266}) {
                        if (checkpass["substring"](6, 11) == "F{not") {
                            if (checkpass.substring(split * 2 * 2, split * 3 * 2) == _again_1) {
                                if (checkpass.substring(12, 16) == this) {
                                    alert("Password Verified");
                                }
                            }
                        }
                    }
                }
            }
        }
    } else {
        alert("Incorrect password");
    }
};
```

Following the substrings you get ```picoCTF{not_this_again_19f266}``` which you can check the page for correctness before submitting.

Flag: ```picoCTF{not_this_again_19f266}```