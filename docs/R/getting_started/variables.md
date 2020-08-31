---
id: variables
title: Variables
---

## What is the Variables in R?

> In computer programming, **[variables](https://en.wikipedia.org/wiki/Variable_(computer_science))** is a ***symbolic name*** which used to store a value.

A variable in R can store an **vectors** or **R-Objects**

A valid variable name consists of **letters**, **numbers**, the **dot(.)**, **underscore(_)** and **comma(,)** characters.

> The variable name should not start with **number(s)** and **underscore**, it's not allowed.

| Variable Name | Validity | Description |
| :-----------: | :------: | :---------: |
| var_name | Valid | Contains **letters** and **underscore** |
| var_name1. | Valid | Contains **letters**, **numbers**, **dot** and **underscore** |
| .var_name, | Valid | Variable name can start with **dot** |
| var.name | Valid | **dot** can be within variable name |
| var_name% | Invalid | Contains **character** `%`, which is not allowed |
| 1var_name | Invalid | Starts with a **number**, which is not allowed |
| .1var_name | Invalid | **Number** should not followed by starting **dot** |
| _var_name | Invalid | Starts with **underscore**, which is not allowed |

> **Reserved words** in R programming also cannot be used as an variable names.

## What is Reserved Words?

**Reserved words** in R programming are set of words that have special meaning and can't be used as variable name.

<u>**Reserved words in R programming**</u>

**`if` `else` `repeat` `while` `function` `for` `in` `next` `break`**

**`TRUE` `FALSE` `NULL` `Inf` `NaN` `NA` `NA_integer_` `NA_real_` `NA_complex_` `NA_character_`** etc.

The list of reserved words can be viewed by typing `help(reserved)` or `?reserved`

```r
# view the list of reserved words
?reserved
```

Where, `if`, `else`, `repeat`, `while`, `function`, `for`, `in`, `next` and `break` are used for conditions, loops and user defined functions.

`TRUE` and `FALSE` are the logical constants in R.

> R is a case sensitive language, Which mean that `TRUE` and `True` are not the same.

Where, the `TRUE` is a reserved word and `True` can be used as a variable name.

```r
# `TRUE` vs `True` as a variable name
TRUE <- "Hello, World!"
print(TRUE)

True <- "Rajesh Detroja"
print(True)
```

produces:

```r
Error in TRUE <- "Hello, World!" :
  invalid (do_set) left-hand side to assignment
TRUE
"Rajesh Detroja"
```

`NULL` represents the absence of a value or an undefined value.

`Inf` is for “Infinity”, for example when **1** is divided by **0**

`NaN` is for “Not a Number”, for example when **0** is divided by **0**

`NA` stands for “Not Available” and is used to represent missing values.

<u>**Note:**</u> Function `help()` or `?` is used to view a manual for in-built R functions.

## How to Assign Variables?

The variables can be assigned values using **leftward**, **rightward** and **equal** to operator.

```r
# Assignment using equal operator
var_x = c(0,2.5,8,10,200)

# Assignment using rightward operator
var_y <- TRUE

# Assignment using leftward operator
c("Rajesh","Detroja") -> var_z
```

The values of the variables can be printed using `print()` or `cat()` functions.

```r
# printing using `print()` function
print(var_x)
print(var_y)
print(var_z)
```

produces:

```r
0.0 2.5 8.0 10.0 200.0
TRUE
"Rajesh" "Detroja"
```

The `cat()` function can be used to concatenate and print things together.

```r
# printing using `cat()` function
cat("The values in `var_x` is:", var_x, "\n")
cat("The values in `var_y` is:", var_y, "\n")
cat("The values in `var_z` is:", var_z, "\n")
```

produces:

```r
The values in `var_x` is: 0 2.5 8 10 200
The values in `var_y` is: TRUE
The values in `var_z` is: Rajesh Detroja
```

<u>**Note:**</u> Character `\n` is used to **print a new line** after the output.

## How to Assign Data Type of Variable?

As said [**earlier**](data-types#what-is-the-data-types-in-r), In R programming, **data type of variable** assigned by the **data type of R-Object**. If *data type of R-Object* changes then *data type of variable* changes too.

```r
# assigning data type to variables
var_x1 <- "Rajesh Detroja"
cat("The class of `var_x1` is: ", class(var_x1), "\n")

var_x2 <- 3.14
cat("Now, the class of `var_x2` is: ", class(var_x2), "\n")

var_x3 <- 3L
cat("Now, The class of `var_x3` is: ", class(var_x3), "\n")

var_x4 <- FALSE
cat("Now, The class of `var_x4` is: ", class(var_x4), "\n")
```

produces:

```r
The class of `var_x1` is:  character
Now, the class of `var_x2` is:  numeric
Now, The class of `var_x3` is:  integer
Now, The class of `var_x4` is:  logical
```

## How to Make List of Current Variables

`ls()` function can be used to list all the available variable in current environment.

```r
# make list of all the available variable in current environment
print(ls())
```

produces:

```r
"True" "var_x" "var_x1" "var_x2" "var_x3" "var_x4" "var_y" "var_z"
```

Moreover, `ls()` function also accept patterns to match the variable names.

```r
# make list of all the available variable in current environment using pattern
print(ls(pattern = "var_x"))
```

produces:

```r
"var_x" "var_x1" "var_x2" "var_x3" "var_x4"
```

The variable starting with `dot(.)` are hidden and can be listed using `all.name = TRUE` arguments to `ls()` function.

```r
# creating a hidden variable
.var_xy <- "Hello World!"

# checking the class of a hidden variable
print(class(.var_xy))

# listing all the variables
print(ls())

# listing all the variables including hidden variable
print(ls(all.name = TRUE))
```

produces:

```r
"character"
"True" "var_x" "var_x1" "var_x2" "var_x3" "var_x4" "var_y" "var_z"
".var_xy" "True" "var_x" "var_x1" "var_x2" "var_x3" "var_x4" "var_y" "var_z"
```


## How to Delete Variable?

`rm()` function can be used to delete a variable.

```r
# deleting the variable `.var_hidden`
rm(.var_xy)

# print deleted variable `.var_hidden`
print(.var_xy)
```

produces:

```r
Error in print(.var_xy) : object '.var_xy' not found
```

**.var_xy** variable is deleted therefore it is not accessible.

```r
# listing all the remaining variables
print(ls())
```

produces:

```r
"True" "var_x" "var_x1" "var_x2" "var_x3" "var_x4" "var_y" "var_z"
```

All the variables in current environment can be deleted by using `rm()` and `ls()` functions together.

```r
# deleting all the variables in current environment
rm(list = ls())

# printing remaining variables
print(ls())
```

produces:

```r
character(0)
```

#### <u>download</u>

[`variables.R`](https://github.com/Rajesh-Detroja/R/blob/master/getting_started/variables.R)
