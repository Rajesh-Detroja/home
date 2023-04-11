Files and Folders Part 2
========================

[](#mkdir)mkdir
---------------

`mkdir` command used to create folder(s)

    mkdir bash
    ls
    

produces:

    bash
    

**Note**: Always use `-` or `_` or `.` etc. to create file's and folder's name. It's better not to use `SPACE`.

    # create multiple folders using `mkdir`
    mkdir bash-folder bash_folder bash.folder bash\ folder
    ls
    

produces:

    bash  'bash folder'   bash-folder   bash.folder   bash_folder
    

**Note**: Always use `\` regular expression to recognize `SPACE` in the folder name.

    # make multiple parent folders using `mkdir`
    mkdir -p test/test1/test_final
    

[](#tree)tree
-------------

`tree` command used to view the structure of the directory

    tree test/
    

produces:

    test/
    `-- test1
        `-- test_final
    
    2 directories, 0 files
    

[](#rm--r)rm -r
---------------

`rm -r` command used to remove folder(s)

    # remove folder
    rm -r bash\ folder/
    

produces:

    rm: remove directory 'bash folder/'? y
    

    # remove multiple folders
    rm -r bash_folder/ bash.folder/ bash-folder/
    

produces:

    rm: remove directory 'bash_folder/'? y
    rm: remove directory 'bash.folder/'? y
    rm: remove directory 'bash-folder/'? y
    

    # remove descendant directories using 'rm -r'
    rm -r test/
    

produces:

    rm: descend into directory 'test/'? y
    rm: descend into directory 'test/test1'? y
    rm: remove directory 'test/test1/test_final'? y
    rm: remove directory 'test/test1'? y
    rm: remove directory 'test/'? y
    

[](#rm--rf)rm -rf
-----------------

`rm -rf` command used to remove the directory forcefully without asking for the permission

    # remove test directory using 'rm -rf'
    rm -rf test/
    

[](#touch)touch
---------------

`touch` command used to create a file

    # create a empty text file using `touch`
    touch file.txt
    ls
    

produces:

    bash  file.txt
    

    # create a multiple text files using `touch`
    touch file-1.txt file_2.txt file.3.txt
    ls
    

produces:

    bash  file-1.txt  file.3.txt  file.txt  file_2.txt
    

[](#rm)rm
---------

`rm` command used to remove file(s)

    # remove `file.txt` using `rm` command
    rm file.txt
    

produces:

    rm: remove regular empty file 'file.txt'? y
    

    # remove multiple files using `rm` command
    rm file-1.txt file_2.txt file.3.txt
    

produces:

    rm: remove regular empty file 'file-1.txt'? y
    rm: remove regular empty file 'file_2.txt'? y
    rm: remove regular empty file 'file.3.txt'? n
    

    ls
    

produces:

    bash  file.3.txt
    

**Note:** Use `Alt + TAB` to change the window.

[](#rm--f)rm -f
---------------

`rm -f` used to remove files forcefully without asking for the permission

    ## remove two text files using `rm -f` command
    touch file1.txt file_2.txt
    ls
    rm -f file1.txt file_2.txt
    ls
    

produces:

    bash  file.3.txt  file1.txt  file_2.txt
    

[](#vi)vi
---------

`vi` command used to create or edit files

`vi` is a `VIM` editor for linux

**Step 1:** Use `vi <file_name>` to open the file for editing

**Step 2:** Use `Insert` key to start editing file

**Step 3:** Use `Esc` key to end editing file

**Step 4:** Use `:wq` to close the file

**Note:** Use `Ctrl + Home key` to go top of the file

**Note:** Use `Ctrl + End key` to go end of the file

**Note:** Double press `D` to delete lines in file while not editing the file

**Note:** Paste content into the file using `Ctrl + Shift + V`

**Note:** Run commands on the file while not editing the file

**Note:** Remove same word in the file using `:%s/<word>//g` command

**Note:** Replace same word in the file using `:%s/<word>/<replaced_word>/g` command

**Note:** Undo the changes in the current session using `:undo` command

**Note:** Redo the changes in the current session using `:redo` command

[](#less)less
-------------

`less` command used to view the content of the file

    # view the file
    less file.3.txt
    

**Step 1:** Use `Enter` or 'Down Key' or 'mouse scroll down' to go down in the file

**Step 2:** Use `Right Key` to go right in the file

**Step 3:** Use `Left Key` to go left in the file

**Step 4:** Use `Up Key` or 'mouse scroll up' to go up in the file

**Step 5:** Use `End Key` to go end of the file

**Step 6:** Use `Home Key` to go start of the file

**Step 7:** Use `q` to close the file
