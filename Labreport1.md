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
**working directory**: `/home` <br />
**explanation of the output**：because there is no further directory behind the cd, so, it will stay in `/home` directory. But if I put a directory name behind the cd then cd will just move to that directory<br />
**error or not**: this is not an error.<br />
## a path to a directory as an argument
**code block**
```
[user@sahara ~]$ cd lecture1/
```
**output**
```
[user@sahara ~/lecture1]$ 
```
**working directory**: `/home` <br />
**explanation of the output**：because I put lecture1 behind cd, which ask the terminal to move to this directory <br />
**error or not**: this is not an error <br />
## a path to a file as an argument
**code block**
```
[user@sahara ~/lecture1]$ cd README 
```
**output**
```
bash: cd: README: Not a directory
```
**working directory**: `/home/lecture1` <br />
**explanation of the output**：because the README.txt is not a directory but a file, cd can not move to a file so it stay in lecture1 <br />
**error or not**: it is an error, because cd can only move to directory, not files. <br />

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
**working directory**: `/home/lecture1` <br />
**explanation of the output**：ls means that to show all the element in the current directory, so it just shows all the directories and files in the lecture1 <br />
**error or not**: this is not an error <br />
## a path to a directory as an argument
**code block**
```
[user@sahara ~/lecture1]$ ls messages/
```
**output**
```
en-us.txt  es-mx.txt  zh-cn.txt
```
**working directory**: `/home/lecture1` <br />
**explanation of the output**：`ls messages/` just shows all the element in the directory messages <br />
**error or not**: this is not an error <br />
## a path to a file as an argument
**code block**
```
[user@sahara ~/lecture1]$ ls README 
```
**output**
```
README
```
**working directory**: `/home/lecture1` <br />
**explanation of the output**：because README is a file, therefore there is no any element in it other than itself, so the ls just shows README itself <br />
**error or not**: this is not an error <br />

# cat 
## no argument
**code block**
```
[user@sahara ~]$ cat
```
**output**
the terminal was stuck in there and I need to press on the control D to free the terminal <br />
*And I also tried typing some text and hit enter* <br />
`[user@sahara ~]$ cat anyways`<br />
*and the out put be* `cat: anyways: No such file or directory`<br />
**working directory**: `/home` <br />
**explanation of the output**：nothing turns out, the terminal was stuck, because cat means read and show the file, but I did put any file or directory follow cat, therefore there is an error appears.<br />
**error or not**: this is an error, because I did not put any file or directory behind it <br />
## a path to a directory as an argument
**code block**
```
[user@sahara ~]$ cat lecture1/
```
**output**
```
cat: lecture1/: Is a directory
```
**working directory**: `/home` <br />
**explanation of the output**：because cat can only read file, but lecture1 is a directory, therefore cat can not read it and turns out an error <br />
**error or not**: this is an error, because cat can only read file, but lecture1 is a directory <br />
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
**working directory**: `/home/lecture1` <br />
**explanation of the output**：cat reads and shows the content in the file that I put behind it <br />
**error or not**: this is not an error <br />









