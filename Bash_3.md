Files and Folders Part 3
========================

[](#head)head
-------------

`head` command used to view number of lines starting at the file

    ## Generate the file `file.3.txt` with 20 lines
    cat file.3.txt
    

produces:

    Line 1
    Line 2
    Line 3
    Line 4
    Line 5
    Line 6
    Line 7
    Line 8
    Line 9
    Line 10
    Line 11
    Line 12
    Line 13
    Line 14
    Line 15
    Line 16
    Line 17
    Line 18
    Line 19
    Line 20
    

    ## view 10 lines starting at the file
    head file.3.txt
    

produces:

    Line 1
    Line 2
    Line 3
    Line 4
    Line 5
    Line 6
    Line 7
    Line 8
    Line 9
    Line 10
    

    ## view 5 lines starting at the Files
    head -n 5 file.3.txt
    

produces:

    Line 1
    Line 2
    Line 3
    Line 4
    Line 5
    

[](#tail)tail
-------------

`tail` command used to view the number of lines at the end of the file

    ## view 10 lines at the end of the file
    tail file.3.txt
    

produces:

    Line 11
    Line 12
    Line 13
    Line 14
    Line 15
    Line 16
    Line 17
    Line 18
    Line 19
    Line 20
    

    ## view 5 lines at the end of the file
    tail -n 5 file.3.txt
    

produces:

    Line 16
    Line 17
    Line 18
    Line 19
    Line 20
    

    ## count lines of the file
    wc -l file.3.txt
    

produces:

    20 file.3.txt
    

    ## view 8 to 12 middle lines of the file
    tail -n +8 file.3.txt | head -n 5
    

produces:

    Line 8
    Line 9
    Line 10
    Line 11
    Line 12
    

[](#cat)cat
-----------

`cat` command used to concatenate content of the two or more files

    ## Create `file1.txt` and `file2.txt`
    vi file1.txt ## Enter "Rajesh" as content
    vi file2.txt ## Enter "Detroja" as content
    cat file1.txt ## `cat` command is also a quick command to view the content of the very small file
    cat file2.txt
    

produces:

    Rajesh
    Detroja
    

    ## Concatenate content of the `file1.txt` and `file2.txt` into `file3.txt`
    cat file1.txt file2.txt > file3.txt
    cat file3.txt
    

produces:

    Rajesh
    Detroja
    

**Note:**: Use `>` symbol to write output into the new file

For example, we wrote the output into the new file `file3.txt`, The new file `file3.txt` is automatically created if already not present.

If `file3.txt` is already present then it will overwrite

If `file3.txt` is already present and you want keep the **original + new** content then use `>>`

    ## Concatenate `file4.txt` into already present `file3.txt`
    vi file4.txt ## Enter "Bioinformatics" as content
    cat file4.txt >> file3.txt
    cat file3.txt
    

produces:

    Rajesh
    Detroja
    Bioinformatics
    

[](#cp)cp
---------

`cp` command used to copy file(s)

    ## copy `file4.txt` to `temp` folder
    mkdir temp
    cp file4.txt temp/
    ls temp/
    cat temp/file4.txt
    

produces:

    file4.txt
    Bioinformatics
    

    ## copy `file4.txt` to `temp` folder and change the file name to `intro.txt`
    cp file4.txt temp/intro.txt
    ls temp/
    cat temp/intro.txt
    

produces:

    file4.txt  intro.txt
    Bioinformatics
    

    ## copy file `file1.txt` and `file2.txt` to `temp` folder
    cp file1.txt file2.txt temp/
    ls temp/
    

produces:

    file1.txt  file2.txt  file4.txt  intro.txt
    

    ## copy file `file3.txt` from back directory to current `temp` directory
    cd temp/
    cp ../file3.txt . ## `.` used to copy into the current directory
    ls
    

produces:

    file1.txt  file2.txt  file3.txt  file4.txt  intro.txt
    

[](#cp--r)cp -r
---------------

`cp -r` command used to copy the folder(s)

    ## Generate folders in the current directory and copy text files
    mkdir folder1 folder2 folder3 folder4
    cp file1.txt folder1/
    cp file2.txt folder2/
    cp file3.txt folder3/
    cp file4.txt folder4/
    

    ## copy `folder4` to `temp` folder using `cp -r`
    cp -r folder4/ temp/
    ls temp/
    ls temp/folder4/
    

produces:

    folder4
    file4.txt
    

    ## copy `folder4` to `temp` folder and rename to `intro`
    cp -r folder4/ temp/intro
    ls temp/
    ls temp/intro/
    

produces:

    folder4  intro
    file4.txt
    

**Note:** Last given folder is the target folder for copying all the given folder(s) before

    ## copy folder `folder1` and `folder2` to `temp` folder
    cp -r folder1/ folder2/ temp/
    ls temp/
    

produces:

    folder1  folder2  folder4  intro
    

    ## copy folder `folder3/` from back directory to current `temp` directory
    cd temp/
    ls ../
    cp -r ../folder3/ .
    ls
    

produces:

    bash  file.3.txt  file1.txt  file2.txt  file3.txt  file4.txt  folder1  folder2  folder3  folder4  temp
    cp -r ../folder3/ .
    folder1  folder2  folder3  folder4  intro
    

[](#mv)mv
---------

`mv` command used to rename files and folders or move (cut and paste) files and folders

    ## rename file `file1.txt` to `intro.txt`
    mv file1.txt intro.txt
    ls
    

produces:

    bash  file.3.txt  file2.txt  file3.txt  file4.txt  folder1  folder2  folder3  folder4  intro.txt  temp
    

    ## rename folder `folder1/` to `intro`
    mv folder1/ intro
    ls
    

produces:

    bash  file.3.txt  file2.txt  file3.txt  file4.txt  folder2  folder3  folder4  intro  intro.txt  temp
    

    ## rename folder `temp/intro` to `temp/folder5` without entering `temp` directory
    ls temp/
    mv temp/intro/ temp/folder5
    ls
    

produces:

    folder1  folder2  folder3  folder4  intro
    folder1  folder2  folder3  folder4  folder5
    

    ## move file `file2.txt` to `temp` folder
    ls
    mv file2.txt temp/
    ls
    ls temp/
    

produces:

    bash  file.3.txt  file2.txt  file3.txt  file4.txt  folder2  folder3  folder4  intro  intro.txt  temp
    bash  file.3.txt  file3.txt  file4.txt  folder2  folder3  folder4  intro  intro.txt  temp
    file2.txt  folder1  folder2  folder3  folder4  folder5
    

    ## move file `file4.txt` and `intro.txt` to `temp` folder
    ls
    mv file4.txt intro.txt temp/
    ls
    ls temp/
    

produces:

    bash  file.3.txt  file3.txt  file4.txt  folder2  folder3  folder4  intro  intro.txt  temp
    bash  file.3.txt  file3.txt  folder2  folder3  folder4  intro  temp
    file2.txt  file4.txt  folder1  folder2  folder3  folder4  folder5  intro.txt
    

    ## move folder `folder2/` to `intro` folder
    ls
    mv folder2 intro/
    ls
    ls intro/
    

produces:

    bash  file.3.txt  file3.txt  folder2  folder3  folder4  intro  temp
    bash  file.3.txt  file3.txt  folder3  folder4  intro  temp
    file1.txt  folder2
    

    ## move folder `folder3/` and `folder4/` to `intro` folder
    ls
    mv folder3 folder4 intro/
    ls
    ls intro/
    

produces:

    bash  file.3.txt  file3.txt  folder3  folder4  intro  temp
    
    bash  file.3.txt  file3.txt  intro  temp
    
    file1.txt  folder2  folder3  folder4
    

[](#ln--s)ln -s
---------------

`ln -s` command used link the file

    ## link file `temp/intro.txt` to current directory 'intro'
    ls
    ls ../temp/
    ln -s ../temp/intro.txt .
    ls
    ll
    

produces:

    file1.txt  file2.txt  folder2  folder3  folder4
    
    file4.txt  folder1  folder2  folder3  folder4  folder5  intro.txt
    
    file1.txt  file2.txt  folder2  folder3  folder4  intro.txt
    
    total 28K
    drwxrwxr-x 5 rajesh rajesh 4.0K Jan 16 16:51 ./
    drwxrwxr-x 5 rajesh rajesh 4.0K Jan 16 16:43 ../
    -rw-rw-r-- 1 rajesh rajesh    7 Jan 16 16:11 file1.txt
    -rw-rw-r-- 1 rajesh rajesh    8 Jan 16 15:30 file2.txt
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder2/
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder3/
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder4/
    lrwxrwxrwx 1 rajesh rajesh   17 Jan 16 16:51 intro.txt -> ../temp/intro.txt
    

**Note::** `-s` option means symbolic link of the file, means if you edit the file `intro.txt` from `intro` folder it change the content in `../temp/intro.txt` as well.

However, If you delete the file `intro.txt` from `intro` folder it will not delete file `../temp/intro.txt`

[](#unlink)unlink
-----------------

`unlink` command used to unlink the linked file

    ## unlink file `intro.txt` using `unlink` command
    ll
    unlink intro.txt
    ls
    

produces:

    total 28K
    drwxrwxr-x 5 rajesh rajesh 4.0K Jan 16 16:51 ./
    drwxrwxr-x 5 rajesh rajesh 4.0K Jan 16 16:43 ../
    -rw-rw-r-- 1 rajesh rajesh    7 Jan 16 16:11 file1.txt
    -rw-rw-r-- 1 rajesh rajesh    8 Jan 16 15:30 file2.txt
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder2/
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder3/
    drwxrwxr-x 2 rajesh rajesh 4.0K Jan 16 16:12 folder4/
    lrwxrwxrwx 1 rajesh rajesh   17 Jan 16 16:51 intro.txt -> ../temp/intro.txt
    
    file1.txt  file2.txt  folder2  folder3  folder4
