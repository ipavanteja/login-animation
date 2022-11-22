# <p align="center">Basic Linux Commands</p>
### 1. mkdir -Make Directory
We can create a new directory with the help of **"mkdir** command.In place of \<dir name> type the name of new directory, you want to create and then press enter.
**Syntax :**<br>
**mkdir \<dir name>**

**Example :**
```
root@0xcamp:~$mkdir new
root@0xcamp:~cd new
root@0xcamp:~/new$
```

### To create multiple directories
**Syntax :**<br>
**mkdir \<dir name1> \<dir name2> \<dir name3>**

**Example :** 
```
root@0xcamp:~$mkdir new new1 new2
root@0xcamp:~$ls -l
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new1
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new2
```
### mkdir Options :
**mkdir -p --parents**<br>
mkdir -p command you can create sub-directories of a directory.

**Example :**
```
root@0xcamp:~$mkdir -p p1/s1
root@0xcamp:~$
root@0xcamp:~$ls -li
drwxr-xr-x 1 root root    4096 Oct 25 21:07  p1
root@0xcamp:~$cd p1
root@0xcamp:~p1$ls -l
drwxr-xr-x 1 root root 4096 Oct 25 21:07 s1
```
**mkdir -v, --verbose**<br>
'mkdir -v' command will print a message with every new file created.

**Example :**
```
root@0xcamp:~$mkdir -v verbose
mkdir: created directory 'verbose'
```
**mkdir -m, --mode=MODE**<br>

With the mkdir -m command, we can give the permissions on the directory you are creating. Access means to give the authority to read(r), write(w), and execute(x).<br>

**Example :**
```
root@0xcamp:~$mkdir -m 777 access
root@0xcamp:~$ls -l
drwxrwxrwx 1 root root    4096 Oct 25 21:15  access
```
### 2. ls - list directory contents
This command lists the contents of a directory with ls.

**Example :**
```
root@0xcamp:~$ ls
file.txt scan.txt
```
### ls Options :

**ls -a command**<br>

In Linux, hidden files start with . (dot) symbol and they are not visible in the regular directory. The (ls -a) command will enlist the whole list of the current directory including the hidden files.
**Example :**
```
root@0xcamp:~$ls -a                      
 .                            .motd_shown    
 ..                           .profile     
 .bash_history                .sudo_as_admin_successful
 .bash_logout  
 .bashrc        
 .cache             
 .landscape     
 .lesshst       
 .local 
```
**ls -l command**<br>

The ls command will only display the files. But if you want your files to be displayed in a long list format, then you can use ls -l command.

**Example :**
```
root@0xcamp:~$ls -l
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new1
drwxr-xr-x 1 root root 4096 Oct 25 18:57 new2
```

Here, as you can see the list in long list format.

- **Columns above indicate specific things:**<br>
   - Column 1 indicates information regarding file permission.
   - Column 2 indicates the number of links to the file.
   - Column 3 & 4 indicates the owner and group information.
   - Column 5 indicayes size of the file in bytes.
   - Column 6 shows th date and time on which the file was recently modified.
   - Column 7 shows the file or directory name.

**ls -s command**<br>

If you want to display your files in descending order (highest at the top) according to their size, then you can use (ls -lhS) command.

**Example :**
```
root@0xcamp:~$ls -lS
-rw-r--r-- 1 root   root 1117150 Oct 22 16:33 -r
drwxr-xr-x 1 root   root    4096 Oct 25 18:59 1
drwxr-xr-x 1 root   root    4096 Oct 26 13:29 dir
drwxr-xr-x 1 root   root    4096 Oct 26 13:29 mk
-rw-r--r-- 1 root   root       0 Oct 26 13:30 text
```

**ls -d */**

If you only want to display the sub-directories excluding all other files, you can use this command.

**Example :**
```
root@0xcamp:~$ls -d */
oxcamp@LAPTOP-MU032EI7:~$ ls -d */
1/  dir/  mk/
```

**ls -g**

If you don't want to display the owner information in your list, then you can exclude this column with the help of this command.
**Example :**
```
root@0xcamp:~$ls -g
total 1092
-rw-r--r-- 1 root  1117150 Oct 22 16:33 -r
drwxr-xr-x 1 root     4096 Oct 25 18:59 1
drwxr-xr-x 1 root     4096 Oct 26 13:29 dir
drwxr-xr-x 1 root     4096 Oct 26 13:29 mk
-rw-r--r-- 1 root        0 Oct 26 13:30 text
root@0xcamp:~$ 
```

**ls -lh**

This command will show you the file sizes in human readable format. Size of the file is very difficult to read when displayed in terms of byte. The (ls -lh)command will give you the data in terms of Mb, Gb, Tb, etc.
**Example :**
```
root@0xcamp:~$ls -lh
total 1.1M
-rw-r--r-- 1 root   root  1.1M  Oct 22 16:33 -r
drwxr-xr-x 1 root   root   4.0K Oct 25 18:59 1
drwxr-xr-x 1 root   root   4.0K Oct 26 13:29 dir
drwxr-xr-x 1 root   root   4.0K Oct 26 13:29 mk
-rw-r--r-- 1 root   root      0 Oct 26 13:30 text
```


**ls -li**<br>

ls -li	This command prints the index number if file is in the first column.
**Example :**
```
root@0xcamp:~$ls -li
total 1092
15199648742825836 -rw-r--r-- 1 root   root   1117150 Oct 22 16:33 -r
48132221017532793 drwxr-xr-x 1 root   root      4096 Oct 25 18:59 1
14918173765857174 drwxr-xr-x 1 root   root      4096 Oct 26 13:29 dir
20547673300070300 drwxr-xr-x 1 root   root      4096 Oct 26 13:29 mk
13229323905593248 -rw-r--r-- 1 root   root         0 Oct 26 13:30 text
```

**ls -r**<br>

It is used to print the list in reverse order.
**Example :**
```
root@0xcamp:~$ls -r
text  mk  dir  1  -r
```

**ls ~**<br>

Linux ls ~ command shows the contents of the home directory. Let us see the example of ls ~ command.

**Example :**
```
