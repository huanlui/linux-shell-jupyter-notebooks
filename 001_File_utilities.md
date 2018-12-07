
# File utilities

Preparing environment. Take into account that _cd_ shell command and other do not work so we have to use _%cd_ instead.


```python
%cd
! rm -r first_dir
```

    /home/dsc


# Exercises


* Create	a	directory	“first_dir”	in	you	home	folder 


```python
! mkdir first_dir
! ls
```

    anaconda3  Downloads		     metastore_db  Repos	     vacio
    basura	   first_dir		     Music	   salida.sh	     Videos
    Data	   first_Dir_2		     one	   size
    derby.log  first_linux_commands.txt  Pictures	   size_of_file.txt
    Desktop    hello_file		     Public	   Templates
    Documents  Historias Antiguas	     R		   uniq_example.txt


 * Create	an	empty	file	“text_file.txt”	inside	“first_dir”	directory.	


```python
%cd first_dir
! touch text_file.txt
! ls
```

    /home/dsc/first_dir
    text_file.txt


* Add	execute	permissions	to	group	users,	and	write	permissions	to	other	users	to	“text_file.txt”	


```python
! ls -alt text_file.txt
! chmod g+x,o+w text_file.txt
! ls -alt text_file.txt
```

    -rw-r--r-- 1 dsc dsc 0 dic  8 00:37 text_file.txt
    -rw-r-xrw- 1 dsc dsc 0 dic  8 00:37 text_file.txt


* Create 3 subdirectories inside “first_dir”: “sub1”, “sub2”, “text_file"


```python
! mkdir sub1 sub2 text_file
! ls
```

    sub1  sub2  text_file  text_file.txt


* Copy the "text_file.txt" file into "sub1" subdirectory


```python
! cp text_file.txt sub1
! ls -R
```

    .:
    sub1  sub2  text_file  text_file.txt
    
    ./sub1:
    text_file.txt
    
    ./sub2:
    
    ./text_file:


* Move the "text_file.txt" into sub2 unser name "text_file.txt.2"


```python
! mv text_file.txt sub2/text_file.txt.2
! ls -R
```

    .:
    sub1  sub2  text_file
    
    ./sub1:
    text_file.txt
    
    ./sub2:
    text_file.txt.2
    
    ./text_file:


* Copy the whole directory "sub1" to "sub3" directory


```python
! cp -r sub1 sub3
! ls -R
```

    .:
    sub1  sub2  sub3  text_file
    
    ./sub1:
    text_file.txt
    
    ./sub2:
    text_file.txt.2
    
    ./sub3:
    text_file.txt
    
    ./text_file:


* Change file name of "first_dir/sub2/text_file.txt.2" to "first_dir/sub2/text_file.txt.backup"


```python
! mv sub2/text_file.txt.2 sub2/text_file.txt.backup
! ls -R
```

    .:
    sub1  sub2  sub3  text_file
    
    ./sub1:
    text_file.txt
    
    ./sub2:
    text_file.txt.backup
    
    ./sub3:
    text_file.txt
    
    ./text_file:


Move "first_dir/sub2/text_file.txt.backup" to "first_dir" directory as hidden file


```python
! mv sub2/text_file.txt.backup .text_file.txt.backup
! ls -Ra
```

    .:
    .  ..  sub1  sub2  sub3  text_file  .text_file.txt.backup
    
    ./sub1:
    .  ..  text_file.txt
    
    ./sub2:
    .  ..
    
    ./sub3:
    .  ..  text_file.txt
    
    ./text_file:
    .  ..


Note: hidden files begin with '.' in linux

* Clean environment 


```python
%cd
! rm -r first_dir
```

    /home/dsc

