---
title: "Some Assembly Required 1"
categories:
  - picoCTF-2021
tags:
  - picoCTF
  - picoCTF-2021
  - web exploitation
---

Problem: http://mercury.picoctf.net:37669/index.html

Solution: 

So going to the webpage you see:
```
<html>
<head>
	<meta charset="UTF-8">
	<script src="G82XCw5CX3.js"></script>
</head>
<body>
	<h4>Enter flag:</h4>
	<input type="text" id="input"/>
	<button onclick="onButtonPress()">Submit</button>
	<p id="result"></p>
</body>
</html>
```

G82XCw5CX3.js:

```
const _0x402c=['value','2wfTpTR','instantiate','275341bEPcme','innerHTML','1195047NznhZg','1qfevql','input','1699808QuoWhA','Correct!','check_flag','Incorrect!','./JIFxzHyW8W','23SMpAuA','802698XOMSrr','charCodeAt','474547vVoGDO','getElementById','instance','copy_char','43591XxcWUl','504454llVtzW','arrayBuffer','2NIQmVj','result'];const _0x4e0e=function(_0x553839,_0x53c021){_0x553839=_0x553839-0x1d6;let _0x402c6f=_0x402c[_0x553839];return _0x402c6f;};(function(_0x76dd13,_0x3dfcae){const _0x371ac6=_0x4e0e;while(!![]){try{const _0x478583=-parseInt(_0x371ac6(0x1eb))+parseInt(_0x371ac6(0x1ed))+-parseInt(_0x371ac6(0x1db))*-parseInt(_0x371ac6(0x1d9))+-parseInt(_0x371ac6(0x1e2))*-parseInt(_0x371ac6(0x1e3))+-parseInt(_0x371ac6(0x1de))*parseInt(_0x371ac6(0x1e0))+parseInt(_0x371ac6(0x1d8))*parseInt(_0x371ac6(0x1ea))+-parseInt(_0x371ac6(0x1e5));if(_0x478583===_0x3dfcae)break;else _0x76dd13['push'](_0x76dd13['shift']());}catch(_0x41d31a){_0x76dd13['push'](_0x76dd13['shift']());}}}(_0x402c,0x994c3));let exports;(async()=>{const _0x48c3be=_0x4e0e;let _0x5f0229=await fetch(_0x48c3be(0x1e9)),_0x1d99e9=await WebAssembly[_0x48c3be(0x1df)](await _0x5f0229[_0x48c3be(0x1da)]()),_0x1f8628=_0x1d99e9[_0x48c3be(0x1d6)];exports=_0x1f8628['exports'];})();function onButtonPress(){const _0xa80748=_0x4e0e;let _0x3761f8=document['getElementById'](_0xa80748(0x1e4))[_0xa80748(0x1dd)];for(let _0x16c626=0x0;_0x16c626<_0x3761f8['length'];_0x16c626++){exports[_0xa80748(0x1d7)](_0x3761f8[_0xa80748(0x1ec)](_0x16c626),_0x16c626);}exports['copy_char'](0x0,_0x3761f8['length']),exports[_0xa80748(0x1e7)]()==0x1?document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)]=_0xa80748(0x1e6):document[_0xa80748(0x1ee)](_0xa80748(0x1dc))[_0xa80748(0x1e1)]=_0xa80748(0x1e8);}
```

I tried reversing the code manually. And let comment during the process. 

```
/// I Have swapped the hex for readable numbers 

// An array
var _0x402c = ['value', '2wfTpTR', 'instantiate', '275341bEPcme', 'innerHTML', '1195047NznhZg', '1qfevql', 'input', '1699808QuoWhA', 'Correct!', 'check_flag', 'Incorrect!', './JIFxzHyW8W', '23SMpAuA', '802698XOMSrr', 'charCodeAt', '474547vVoGDO', 'getElementById', 'instance', 'copy_char', '43591XxcWUl', '504454llVtzW', 'arrayBuffer', '2NIQmVj', 'result'];
// A function(x,y) which returns array[x-]
var _0x4e0e = function(_0x553839, _0x53c021) {
    _0x553839 = _0x553839 - 470;
    let _0x402c6f = _0x402c[_0x553839];
    return _0x402c6f;
};

// Function function(array,627907)
(function(_0x76dd13, _0x3dfcae) {
	// function(x,y) array
    var _0x371ac6 = _0x4e0e;
    while (!![]) {
        try {
			var _0x478583 = -parseInt(_0x371ac6(491)) + parseInt(_0x371ac6(493)) + -parseInt(_0x371ac6(475)) * -parseInt(_0x371ac6(473)) + -parseInt(_0x371ac6(482)) * -parseInt(_0x371ac6(483)) + -parseInt(_0x371ac6(478)) * parseInt(_0x371ac6(480)) + parseInt(_0x371ac6(472)) * parseInt(_0x371ac6(490)) + -parseInt(_0x371ac6(485));
			// _0x478583 = NaN
            if (_0x478583 === _0x3dfcae) // 627907
                break;
            else
                _0x76dd13['push'](_0x76dd13['shift']()); // Runs and shifts the array
        } catch (_0x41d31a) {
            _0x76dd13['push'](_0x76dd13['shift']());
        }
    }
}(_0x402c, 627907));

// Array is currently 

//var _0x402c = ["instance", "copy_char", "43591XxcWUl", "504454llVtzW", "arrayBuffer", "2NIQmVj", "result", "value", "2wfTpTR", "instantiate", "275341bEPcme", "innerHTML", "1195047NznhZg", "1qfevql", "input", "1699808QuoWhA", "Correct!", "check_flag", "Incorrect!", "./JIFxzHyW8W", "23SMpAuA", "802698XOMSrr", "charCodeAt", "474547vVoGDO", "getElementById"]

let exports;
(async()=>{
    var _0x48c3be = _0x4e0e;
	console.log(_0x48c3be(489));
    let _0x5f0229 = await fetch(_0x48c3be(489)) // await fetch(./JIFxzHyW8W)
      , _0x1d99e9 = await WebAssembly[_0x48c3be(479)](await _0x5f0229[_0x48c3be(474)]()) // await WebAssembly.instantiate(fetch(./JIFxzHyW8W).arrayBuffer())
      , _0x1f8628 = _0x1d99e9[_0x48c3be(470)]; //await WebAssembly.instantiate(fetch(./JIFxzHyW8W).arrayBuffer()).instance
    exports = _0x1f8628['exports'];
}
)();
function onButtonPress() {
    var _0xa80748 = _0x4e0e;
    let _0x3761f8 = document['getElementById'](_0xa80748(484))[_0xa80748(477)]; //document.getElementById("input").value;
    for (let i = 0; i < _0x3761f8['length']; i++) {
        exports[_0xa80748(471)](_0x3761f8[_0xa80748(492)](i), i); // exports.copy_char(document.getElementById("input").value.charCodeAt(i))
    }
    exports['copy_char'](0, _0x3761f8['length']), // exports.copy_char(0,document.getElementById("input").value.length),
    exports[_0xa80748(487)]() == 1 ? document[_0xa80748(494)](_0xa80748(476))[_0xa80748(481)] = _0xa80748(486) : document[_0xa80748(0x1ee)](_0xa80748(476))[_0xa80748(481)] = _0xa80748(488); //exports.check_flag() == 1 ? document.getElementById("result").innerHTML = "Correct!" : document.getElementById("result").innerHTML = "Incorrect"; 

}

```

I dont think I have everything converted correctly but the part of note is ```WebAssembly.instantiate(fetch(./JIFxzHyW8W).arrayBuffer())```

Mainly the ```./JIFxzHyW8W``` part. I couldnt get the WebAssembly part of the syntax correct but I went to ./JIFxzHyW8W and it downloaded a file. 

File: [THE_FILE](https://github.com/Yorzaren/ctf/raw/master/picoCTF-2021/solution-files/JIFxzHyW8W "Download file")

Which had the flag which was readable.

![no-alignment]({{ '/picoCTF-2021/solution-files/some-assembly-required-1.jpg' | absolute_url }})

Flag: ```picoCTF{a8bae10f4d9544110222c2d639dc6de6}```