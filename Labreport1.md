# cd <br />
## no argument
**code block**
```
[user@sahara ~]$ cd
```
**output**
```
[user@sahara ~]$ 
```
**working directory**
home 
## a path to a directory as an argument
**code block**
```
[user@sahara ~]$ cd lecture1/
```
**output**
```
[user@sahara ~/lecture1]$ 
```
## a path to a file as an argument
**code block**
```
[user@sahara ~/lecture1]$ cd README 
```
**output**
```
bash: cd: README: Not a directory
```
# ls <br />
## no argument
**code block**
```
[user@sahara ~/lecture1]$ ls
```
**output**
```
Hello.class  Hello.java  messages  README
```
## a path to a directory as an argument
**code block**
```
[user@sahara ~/lecture1]$ ls messages/
```
**output**
```
en-us.txt  es-mx.txt  zh-cn.txt
```
## a path to a file as an argument
**code block**
```
[user@sahara ~/lecture1]$ ls README 
```
**output**
```
README
```
# cat 
## no argument
**code block**
```
[user@sahara ~]$ cat
```
**output**
the terminal was stuck in there and I need to press on the control D to free the terminal 
## a path to a directory as an argument
**code block**
```
[user@sahara ~]$ cat lecture1/
```
**output**
```
cat: lecture1/: Is a directory
```
## a path to a file as an argument
**code block**
```
[user@sahara ~/lecture1]$ cat README 
```
**output**
```
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```









