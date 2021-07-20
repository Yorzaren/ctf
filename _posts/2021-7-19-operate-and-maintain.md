---
title: "CyberForce 2021 - Operate and Maintain"
categories:
  - CyberForce
tags:
  - CyberForce
  - CyberForce-2021
  - CyberForce Adventurer
---

# Operate and Maintain
One of the categories in the Department of Energy's CyberForce Program - Conquer the Hill: Adventurer Edition 2021. I was busy and didn't have the time to focus on this category.

[CyberForce 2021 Writeup](/ctf/cyberforce/cyberforce-2021-adventurer-writeup/)

{% include toc %}

## Operate and Maintain: Anomaly 6 (20pts)
You have been provided a file of error logs upon the suspicion of a potential SQL injection. Your job is to identify the error most likely to be associated with the attack, knowing the usual trends that an SQL injection will have and the errors it may produce. What type of SQL injection was attempted here? Syntax hint: Format your answer as “[type]-based injection” 

### Solution

Relevant Log: 
```
[Mon Jun 29 11:30:22.708746 2020] [php7:notice] [pid 1534] [client ::1:51340] or 1 =1 , referer: http://localhost/tester.php
[Mon Jun 29 11:35:07.775141 2020] [php7:notice] [pid 1532] [client ::1:51367] Failed attempt. Username:  , referer: http://localhost/tester.php
[Mon Jun 29 11:35:07.775386 2020] [php7:notice] [pid 1532] [client ::1:51367] 'or '1' = '2, referer: http://localhost/tester.php
[Mon Jun 29 11:35:07.775396 2020] [php7:notice] [pid 1532] [client ::1:51367]  Password: , referer: http://localhost/tester.php
[Mon Jun 29 11:35:07.775404 2020] [php7:notice] [pid 1532] [client ::1:51367] 'or '1' = '2, referer: http://localhost/tester.php
[Mon Jun 29 11:38:25.291250 2020] [php7:notice] [pid 1534] [client ::1:51436] Failed attempt. Username:  , referer: http://localhost/tester.php
[Mon Jun 29 11:38:25.291464 2020] [php7:notice] [pid 1534] [client ::1:51436] ' or '1' = '1;#, referer: http://localhost/tester.php
[Mon Jun 29 11:38:25.291474 2020] [php7:notice] [pid 1534] [client ::1:51436]  Password: , referer: http://localhost/tester.php
[Mon Jun 29 11:38:25.291482 2020] [php7:notice] [pid 1534] [client ::1:51436] , referer: http://localhost/tester.php
[Mon Jun 29 11:39:25.487544 2020] [php7:notice] [pid 1534] [client ::1:51440] Failed attempt. Username:  , referer: http://localhost/tester.php
[Mon Jun 29 11:39:25.487761 2020] [php7:notice] [pid 1534] [client ::1:51440] ' or '1' = '1"; #, referer: http://localhost/tester.php
[Mon Jun 29 11:39:25.487772 2020] [php7:notice] [pid 1534] [client ::1:51440]  Password: , referer: http://localhost/tester.php
[Mon Jun 29 11:39:25.487791 2020] [php7:notice] [pid 1534] [client ::1:51440] , referer: http://localhost/tester.php
```

Ans: `Boolean-based injection`

## Operate and Maintain: Anomaly 17 (20pts)
Your organization is investigating some suspicious activities that were performed by a recently terminated employee. You have been provided with a SQLite file that corresponds to a snapshot of a personnel database for the organization. The employee in question is known to be an Executive working in the “ABC” division, but you will need to access the database to find that employee’s e-mail address. What is the e-mail address?

Syntax hint: include the full email string. E.g., apples@bananas.com

## Operate and Maintain: Anomaly 24 (20pts)
Below is a SQL query and data output from it’s run. What SQL function would you use to return the ip address in dot-decimal notation? Your answer should be formatted in all lower case and in the following style: sql_function(net.ip_address)

SELECT u.id, u.user, u.user_email, u.user_phone, net.ip_address
FROM user_data as u 
JOIN network_history as net
ON u.id = u.user_id
WHERE u.user="takealookatthesehands"

1234810, "lookathesehands", "dbyrne@mymail.com", "555-657-5309", 3232235777

## Operate and Maintain: Anomaly 30 (40pts)
Construct a SQL query that would provide all the database records that contain the city name of Springfield, the state of Illinois, and the “Paid” field set to FALSE.
The table name for your query should be [Customers].

**Please note, this question can have numerous answers. We know this can be frustrating, so we have increased the number of attempts allowed to boost a competitor's chance of obtaining the correct answer**

## Operate and Maintain: Anomaly 36 (50pts)
Given the Windows Event log file provided (eventlog.evtx), you are expected to find the source of malicious activity that was recorded in the log. The hacker launched an exploit embedded in an otherwise innocuous command. You must find either of the two exploit attempts, and answer the question – what command was run to create the process that launched the malicious command?

Hint: Look for a particularly abnormal command line entry – and the answer should be the command that created that process, not the malicious process itself.

syntax hint: answer is not case sensitive, include special characters

## Operate and Maintain: Anomaly 38 (50pts)
You were recently hired in a technical support role at a big famous company that will impress all your friends and family. This company uses OSQuery [1] to help gather information on the user endpoints of their organization. 

You have been asked to write an OSQuery query to gather the following information about patches applied to Windows machines in your organization. 

Information requested: Name of the host the patch was installed on, the KB ID of the patch, and the date when the patch was installed. 

For your answer, submit the query. Make sure it includes a semicolon ( ; ) at the end.  

Note: For this question, you should be able to answer it without using actually installing OSQuery, but feel free to do so on a Windows machine and experiment. 

[1]: https://osquery.io/

## Operate and Maintain: Anomaly 11 (100pts)
You received an advisory from the vendor of your HMI software encouraging you to patch their software.  You’re not sure whether it applies because it looks like you have several versions of the application installed and someone has renamed them.  Can you figure out the right one to patch to avoid a compromise?

syntax hint: no spaces

## Operate and Maintain: Anomaly 37 (100pts)
Analyze the code snippet (snippet.c) from a vulnerable version of the Python source code and look for the buffer overflow vulnerability that exists in the code. What line number in the code would create the overflow condition?

Hint: Look through the provided code and look for areas where there is data being copied from one buffer to another and look for missing error/size checks.

syntax hint: this answer will be a number 