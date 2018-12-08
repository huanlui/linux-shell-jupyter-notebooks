
# File utilities

Preparing environment. Take into account that _cd_ shell command and other do not work so we have to use _%cd_ instead.


```python
%cd
! rm -r first_dir
```

    /home/dsc
    rm: cannot remove 'first_dir': No such file or directory


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

    -rw-r--r-- 1 dsc dsc 0 dic  8 01:00 text_file.txt
    -rw-r-xrw- 1 dsc dsc 0 dic  8 01:00 text_file.txt


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

* Use help to find out how to get the list of subdirectories limited to 2 sublevels by using “tree” command


```python
%cd
! tree -d -L 2
```

    /home/dsc
    [01;34m.[00m
    ├── [01;34manaconda3[00m
    │   ├── [01;34mbin[00m
    │   ├── [01;34mcompiler_compat[00m
    │   ├── [01;34mconda-meta[00m
    │   ├── [01;34mdoc[00m
    │   ├── [01;34menvs[00m
    │   ├── [01;34metc[00m
    │   ├── [01;34minclude[00m
    │   ├── [01;34mlib[00m
    │   ├── [01;34mlibexec[00m
    │   ├── [01;34mman[00m
    │   ├── [01;34mmkspecs[00m
    │   ├── [01;34mphrasebooks[00m
    │   ├── [01;34mpkgs[00m
    │   ├── [01;34mplugins[00m
    │   ├── [01;34mqml[00m
    │   ├── [01;34mshare[00m
    │   ├── [01;34mssl[00m
    │   ├── [01;34mtranslations[00m
    │   ├── [01;34mvar[00m
    │   └── [01;34mx86_64-conda_cos6-linux-gnu[00m
    ├── [01;34mbasura[00m
    │   ├── [01;34mbasura2[00m
    │   └── [01;34mfirst_dir[00m
    ├── [01;34mData[00m
    │   ├── [01;34mairline_tickets[00m
    │   ├── [01;34mchallenge[00m
    │   ├── [01;34mopentraveldata[00m
    │   ├── [01;34mshell[00m
    │   └── [01;34mus_dot[00m
    ├── [01;34mDesktop[00m
    ├── [01;34mDocuments[00m
    ├── [01;34mDownloads[00m
    ├── [01;34mfirst_dir[00m
    │   ├── [01;34msub1[00m
    │   ├── [01;34msub2[00m
    │   ├── [01;34msub3[00m
    │   └── [01;34mtext_file[00m
    ├── [01;34mfirst_Dir_2[00m
    │   ├── [01;34msub1[00m
    │   ├── [01;34msub3[00m
    │   └── [01;34mtext_file[00m
    ├── [01;34mHistorias Antiguas[00m
    ├── [01;34mmetastore_db[00m
    │   ├── [01;34mlog[00m
    │   ├── [01;34mseg0[00m
    │   └── [01;34mtmp[00m
    ├── [01;34mMusic[00m
    ├── [01;34mone[00m
    │   ├── [01;34mb[00m
    │   ├── [01;34mc[00m
    │   ├── [01;34mcarpetaDestino[00m
    │   ├── [01;34mtwo[00m
    │   └── [01;34mtwoCopia[00m
    ├── [01;34mPictures[00m
    ├── [01;34mPublic[00m
    ├── [01;34mR[00m
    │   └── [01;34mx86_64-pc-linux-gnu-library[00m
    ├── [01;34mRepos[00m
    │   ├── [01;34m0001_Ejercicio_shell[00m
    │   ├── [01;34mcsvkit[00m
    │   ├── [01;34mfirst_dir[00m
    │   ├── [01;34mhello-world-master-datascience[00m
    │   ├── [01;34mlinux-shell-jupyter-notebooks[00m
    │   ├── [01;34mplaying-with-linux-shell[00m
    │   ├── [01;34mpostgres[00m
    │   └── [01;34mtesting[00m
    ├── [01;34mTemplates[00m
    ├── [01;34mvacio[00m
    │   └── [01;34motrahija[00m
    └── [01;34mVideos[00m
    
    71 directories


Note: -d: only folders. -L: depth.

* Clean environment 


```python
%cd
! rm -r first_dir
```

    /home/dsc

