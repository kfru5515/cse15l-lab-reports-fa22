LabReport1 <br> 
HYEONJUN JUN <br>
A17181983
---
1.Share an example of using the command with no arguments.<br>
cd: 
```
# code block
[user@sahara ~]$ cd

Explain output:
no output shows up but it
changes to the home directory.
```
ls:
```
# code block
[user@sahara ~]$ ls
lecture1

Explain output:
show up lists of the current directory.
```
cat:
```
# code block
[user@sahara ~]$ cd cat

Explain output:
When we run `cat` command, it shows empty space for new user input.
we can type text. when we exit this mod, we need to press Control + D 
```
---
2.Share an exmaple of using the command with a path to a directory as an argument.<br>
cd: 
```
# code block
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$

Explain output:
when we run cd path to a directory, our current working directory
is changed to a specified directory.
```
ls:
```
# code block
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README

Explain output:
when we run ls with a path to a directory, it lists the files and
directories contained within the specified directory. 
```
cat:
```
# code block
[user@sahara ~]$ cat lecture1/
cat: lecture1/: Is a directory

Explain output:
Error Because `cat` command with a directory path as an
argument because `cat` is used to display file.
```
3.Share an example of using the command with a path to a file as an argument. <br>
cd: 
```
# code block
[user@sahara ~/lecture1/messages]$ cd zh-cn.txt 
bash: cd: zh-cn.txt: Not a directory

Explain output:
when we run `cd` to a txt file and show up not a directory because
`cd` command is used to change directory. 
```
ls:
```
# code block
[user@sahara ~/lecture1/messages]$ ls es-mx.txt 
es-mx.txt

Explain output:
when we run `ls` command, it displays information about that file.
show it's only show es-mx.txt file
```
cat:
```
# code block
[user@sahara ~/lecture1/messages]$ cat es-mx.txt 
¡Hola Mundo!

Explain output:
When we run `cat` command, it displays the contents of the specified
file "es-mx.txt" so it show up ¡Hola Mundo!
```
