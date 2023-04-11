Files and Folders Part 1
========================

[](#ls)ls
---------

`ls` command used to list files and folders in the current directory.

    # list files and folders in current directory
    ls
    

produces:

    bash  bash.txt
    

Here, `bash` is a folder and `bash.txt` is a text file.

[](#--help)\--help
------------------

`--help` option can be use to view more options of any linux command.

    # view more options of `ls` command
    ls --help
    

produces:

    Usage: ls [OPTION]... [FILE]...
    List information about the FILEs (the current directory by default).
    Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.
    
    Mandatory arguments to long options are mandatory for short options too.
      -a, --all                  do not ignore entries starting with .
      -A, --almost-all           do not list implied . and ..
          --author               with -l, print the author of each file
      -b, --escape               print C-style escapes for nongraphic characters
          --block-size=SIZE      with -l, scale sizes by SIZE when printing them;
                                   e.g., '--block-size=M'; see SIZE format below
    
    ...
    

  
  

**Note**: In linux, hidden files and folders are always starting with **`.`**

[](#ls--a)ls -a
---------------

`ls -a` command used to list hidden files and folders in the current directory.

    # list hidden files and folders in the current directory
    ls -a
    

produces:

    .  ..  .bash_file.txt  .bash_folder  bash  bash.txt
    

Here, `.bash_folder` is a hidden folder and `.bash_file.txt` is a hidden text file.

[](#ls--l)ls -l
---------------

`ls -a` command used to list files and folders in the current directory with detailed information.

    # list files and folders in the current directory with detailed information
    ls -a
    

produces:

    total 4.0K
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 13 16:30 bash
    -rw-rw-r-- 1 rajesh rajesh    0 Jan 13 16:30 bash.txt
    

[](#ls--al)ls -al
-----------------

`ls -al` command used to list hidden files and folders in the current directory with detailed information.

    # list hidden files and folders in the current directory with detailed information
    ls -al
    

produces:

    total 16K
    drwxrwxr-x  4 rajesh rajesh 4.0K Jan 13 16:51 .
    drwxrwxr-x 10 rajesh rajesh 4.0K Jan 13 16:30 ..
    -rw-rw-r--  1 rajesh rajesh    0 Jan 13 16:51 .bash_file.txt
    drwxrwxr-x  2 rajesh rajesh 4.0K Jan 13 16:51 .bash_folder
    drwxrwxr-x  2 rajesh rajesh 4.0K Jan 13 16:30 bash
    -rw-rw-r--  1 rajesh rajesh    0 Jan 13 16:30 bash.txt
    

[](#ll)ll
---------

`ll` command is alias command of `ls -al`

`ll` command used to list all the files and folders in the current directory with detailed information.

    ll
    

produces:

    total 16K
    drwxrwxr-x  4 rajesh rajesh 4.0K Jan 13 16:51 ./
    drwxrwxr-x 10 rajesh rajesh 4.0K Jan 13 16:30 ../
    -rw-rw-r--  1 rajesh rajesh    0 Jan 13 16:51 .bash_file.txt
    drwxrwxr-x  2 rajesh rajesh 4.0K Jan 13 16:51 .bash_folder/
    drwxrwxr-x  2 rajesh rajesh 4.0K Jan 13 16:30 bash/
    -rw-rw-r--  1 rajesh rajesh    0 Jan 13 16:30 bash.txt
    

[](#ls--lt)ls -lt
-----------------

`ls -lt` command used to list files and folders in the current directory and sort it by modification (created/edited) time.

    ls -lt
    

produces:

    total 4.0K
    -rw-rw-r-- 1 rajesh rajesh    0 Jan 13 16:30 bash.txt
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 13 16:30 bash
    

[](#cd)cd
---------

`cd` command used to change the directory

    # go to home directory from current directory
    cd
    

**Note:** Use `TAB` to complete the name of the files and folders written after any linux command

    # go to `bash` directory using `cd` command
    cd bash/
    

**Note:** Use double `TAB` to list files and folders of written directory after any linux command

    # go to given path directory using `cd` command
    cd learnings/linux/bash/
    

    # go to parent (directory that is 1 level back) directory
    cd ..
    

    # go to directory that is 2 level back
    cd ../../
    

[](#clear)clear
---------------

`clear` command used to clear the current terminal screen

[](#pwd)pwd
-----------

`pwd` command used to get the path (location) of the current directory

**Note:** New terminal tab can be opened using `ctrl + shift + t` **or** Right click on the current terminal and the click on **New Tab**
