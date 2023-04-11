Handy Linux Commands
====================

### [](#how-to-remove-rows-based-on-values-of-multiple-columns)How to remove rows based on values of multiple columns?

Create a new file called `input.tsv` with following content:

    A/G C/C T/T
    C/C G/G T/G
    T/G T/T G/G
    A/G C/C G/G
    G/G G/T A/G
    A/C A/T T/A
    

Now, remove rows contains `G/G` and `A/G` in the columns `1` and `3` respectively.

    awk '!($1=="G/G" && $3=="A/G")' input.tsv
    

produces:

    A/G C/C T/T
    C/C G/G T/G
    T/G T/T G/G
    A/G C/C G/G
    A/C A/T T/A
    

Now, remove rows contains `A/G`, `C/C` and `T/T` in the columns `1`, `2` and `3` respectively.

    awk '!($1=="A/G" && $2=="C/C" && $3=="T/T")' input.tsv
    

produces:

    C/C G/G T/G
    T/G T/T G/G
    A/G C/C G/G
    G/G G/T A/G
    A/C A/T T/A
