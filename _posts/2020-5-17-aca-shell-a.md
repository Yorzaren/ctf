---
title: "Aca-Shell-A"
categories:
  - picoCTF-2018
tags:
  - picoCTF
  - picoCTF-2018
  - general
---

Problem: It's never a bad idea to brush up on those linux skills or even learn some new ones before you set off on this adventure! Connect with ```nc 2018shell.picoctf.com 58422```.

Solution: 

```nc 2018shell.picoctf.com 58422```

Read the message and type ```echo 'Help Me!'```

The system asked if you've looked for files.

```ls``` to look for the files. 

Directories:
```
blackmail                                                       
executables                                                     
passwords                                                       
photos                                                          
secret```

Let's look in secret. ```cd secret```

Now ```ls```

The order is the remove files and sabatoge them.

```rm intel_1```

Get the exe files from the friend. ```echo 'Drop it in!'```

Run the following commands to get to the file. 

Code: get to directory called executables, find the files in it and then run a program called "dontLookHere"

```cd .. 

cd executables

ls

./dontLookHere
```

```whoami``` alt to echo

```cd ..``` to get out.

```cp /tmp/TopSecret passwords``` copy to a directory called passwords

```ls``` to find the name of the file and ```cat TopSecret``` to read the file.

TopSecret:
```
Major General John M. Schofield's graduation address to the graduating class of 1879 at West Point is as follows: The disci
pline which makes the soldiers of a free country reliable in battle is not to be gained by harsh or tyrannical treatment.On
 the contrary, such treatment is far more likely to destroy than to make an army.It is possible to impart instruction and g
ive commands in such a manner and such a tone of voice as to inspire in the soldier no feeling butan intense desire to obey
, while the opposite manner and tone of voice cannot fail to excite strong resentment and a desire to disobey.The one mode 
or other of dealing with subordinates springs from a corresponding spirit in the breast of the commander.He who feels the r
espect which is due to others, cannot fail to inspire in them respect for himself, while he who feels,and hence manifests d
isrespect towards others, especially his subordinates, cannot fail to inspire hatred against himself.                      
picoCTF{CrUsHeD_It_4e355279}
```

Flag: ```picoCTF{CrUsHeD_It_4e355279}```