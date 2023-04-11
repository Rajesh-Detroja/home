Searching Part 1
================

[](#grep)grep
-------------

`grep` command is used to search for patterns into the file.

    # make folder 'grep_learning'
    mkdir grep_learning
    

Go to `grep_learning` folder.

Generate file `file1.txt` containing following content:

    ostechnix
    Ostechnix
    o$technix
    linux
    linus
    unix
    technology
    hello world
    HELLO world
    

    # search lines containing `nix` in file1.txt
    grep "nix" file1.txt
    

produces:

    ostechnix
    Ostechnix
    o$technix
    unix
    

    # search lines containing `nix` in file1.txt and print line numbers
    grep -n "nix" file1.txt
    

produces:

    1:ostechnix
    2:Ostechnix
    3:o$technix
    6:unix
    

    # search lines containing two words `hello world` in file1.txt
    grep "hello world" file1.txt
    

produces:

    hello world
    

Please note that `grep` is **case-sensitive**. For example, when you search for `hello world`, it is not going to display lines the contains uppercase letters i.e `HELLO world`.

    # search lines containing two words `hello world` in file1.txt without case-sensitive
    grep -i "hello world" file1.txt
    

produces:

    hello world
    HELLO world
    

    # search lines containing `nix` using `|` and multiple commands
    cat file1.txt | grep "nix"
    

produces:

    ostechnix
    Ostechnix
    o$technix
    unix
    

    # search lines containing `nix` and `tech` using `|` and multiple commands
    cat file1.txt | grep "nix" | grep "tech"
    

produces:

    ostechnix
    Ostechnix
    o$technix
    

**Note:** `|` used to apply multiple linux commands in a single-line.

    # search lines containing `nix` and `tech` using -e option of `grep`
    grep -e "nix" -e "tech" file1.txt
    

produces:

    ostechnix
    Ostechnix
    o$technix
    unix
    technology
    

**Note:** `-e` helps to search multiple words without using `|`

    # print lines containing `l` at beginning of the lines in file1.txt
    grep "^l" file1.txt
    

produces:

    linux
    linus
    

`^` - used to search at the beginning of the line.

    # print lines containing `l` at end of the lines in file1.txt
    grep "x$" file1.txt
    

produces:

    ostechnix
    Ostechnix
    o$technix
    linux
    unix
    

`$` - used to search at the end of the line.
