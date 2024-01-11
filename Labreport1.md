# cd <br />
**no argument**
```
[user@sahara ~]$ cd
```
**output**
```
[user@sahara ~]$ 
```
**a path to a directory as an argument**
```
[user@sahara ~]$ cd lecture1/
```
**output**
```
[user@sahara ~/lecture1]$ 
```
**a path to a file as an argument**
```
[user@sahara ~/lecture1]$ cd README 
```
**output**
```
bash: cd: README: Not a directory
```
# ls <br />
**no argument**
```
[user@sahara ~/lecture1]$ ls
```
**output**
```
Hello.class  Hello.java  messages  README
```
**a path to a directory as an argument**
```
[user@sahara ~/lecture1]$ ls messages/
```
**output**
```
en-us.txt  es-mx.txt  zh-cn.txt
```
**a path to a file as an argument**
```
[user@sahara ~/lecture1]$ ls README 
```
**output**
```
README
```
# cat 
**no argument**
```
[user@sahara ~]$ cat
```
**output**
```
the terminal was stuck in there and I need press on the control D to free the terminal 
```
**a path to a directory as an argument**
```
[user@sahara ~]$ cat lecture1/
```
**output**
```
cat: lecture1/: Is a directory
```
**a path to a file as an argument**
```
[user@sahara ~/lecture1]$ cat README 
```
**output**
```
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```









