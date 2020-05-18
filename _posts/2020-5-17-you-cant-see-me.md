---
title: "you can't see me"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - general
---

Problem: '...reading transmission... Y.O.U. .C.A.N.'.T. .S.E.E. .M.E. ...transmission ended...' Maybe something lies in /problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f.

Solution: 

Using the shell server ```cd /problems/you-can-t-see-me_4_8bd1412e56df49a3c3757ebeb7ead77f```

Use ```ls -la``` to see all the files.

Returns:
```
drwxr-xr-x   2 root       root        4096 Mar 25  2019 .
-rw-rw-r--   1 hacksports hacksports    57 Mar 25  2019 .                                                                  
drwxr-x--x 556 root       root       53248 Mar 25  2019 ..
```

We want to see ```.``` but it also the name of the directory and cat doesnt like that. So pass it by using ```cat .*```

Return:
```
cat: .: Is a directory                                                                                                     
picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}                                                                   
cat: ..: Permission denied                                                                                                 
```

Flag: ```picoCTF{j0hn_c3na_paparapaaaaaaa_paparapaaaaaa_22f627d9}```