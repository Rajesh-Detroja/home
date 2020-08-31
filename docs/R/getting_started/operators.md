---
id: operators
title: Operators
---

## What is **Operators** in R?

> An **operator** is a **symbol** that helps R compiler to perform mathematical or logical expressions.

## What are the Types of Operators in R?

There are **5** types of operators in R.

### 1. Arithmetic Operators

The **Arithmetic operators** used to perform mathematical operations like `Addition`, `Subtraction`, `Multiplication`, `Division`, `Integer Division`, `Modulus` and `Exponent`

Following table depicts all the Arithmetic Operators in R:

| Operator | Operation | Example  |
| :-------------: |:-------------:| :-----:|
| **`+`** | Addition | `10 + 5 = 15` |
| **`-`** | Subtraction | `10 - 5 = 5` |
| **`*`**| Multiplication | `10 * 5 = 50` |
| **`/`**| Division | `10 / 5 = 2` |
| **`%/%`** | Integer Division – Same as Division. but it returns only integer value without decimals | `10 %/% 3 = 3` <br> If 10 divided by 3 will produce 3.33, but the Integer division operator will return only Integer (3) and not with decimals (3.33)|
| **`%%`** | Modulus - Returns the remainder after the division | `10 %% 5 = 0`, Here, remainder is zero. <br> `10 %% 3 = 1`, Here, remainder is one.|
| **`^`**| Exponent - Returns the Power of One variable against the other | `10 ^ 3 = 1000` (Means 10 Power 3) |

#### <u>Addition, Subtraction, Multiplication and Division of two numbers</u>

```r
# addition, subtraction, multiplication and division of two numbers
var_x <- 20
var_y <- 10

var_add <- var_x + var_y
var_sub <- var_x - var_y
var_mul <- var_x * var_y
var_div <- var_x / var_y

cat("Addition: ", var_add, "\n")
cat("Subtraction: ", var_sub, "\n")
cat("Multiplication: ", var_mul, "\n")
cat("Division: ", var_div, "\n")
```

produces:

```r
Addition: 30
Subtraction: 10
Multiplication: 200
Division: 2
```

#### <u>Addition, Subtraction, Multiplication and Division of two vectors</u>

```r
# addition, subtraction, multiplication and division of two vectors
var_x <- c(4, 3.14, 8, 10)
var_y <- c(2, 2, 3, 4)

var_add <- var_x + var_y
var_sub <- var_x - var_y
var_mul <- var_x * var_y
var_div <- var_x / var_y

cat("Addition: ", var_add, "\n")
cat("Subtraction: ", var_sub, "\n")
cat("Multiplication: ", var_mul, "\n")
cat("Division: ", var_div, "\n")
```

produces:

```r
Addition: 6 5.14 11 14
Subtraction: 2 1.14 5 6
Multiplication: 8 6.28 24 40
Division: 2 1.57 2.666667 2.5
```

#### <u>Integer division, Modulus and Exponent of two vectors</u>

```r
# integer division, modulus and exponent of two vectors
var_x <- c(2, 3.5, 5, 6)
var_y <- c(4, 2, 3, 4)

var_int_div <- var_x %/% var_y
var_mod <- var_x %% var_y
var_expo <- var_x ^ var_y

cat("Integer division: ", var_int_div, "\n")
cat("Modulus: ", var_mod, "\n")
cat("Exponent: ", var_expo, "\n")
```

produces:

```r
Integer division: 0 1 1 1
Modulus: 2 1.5 2 2
Exponent: 16 12.25 125 1296
```

> When using Integer Division (`%/%`) operator, the results is rounded integer value. Float or decimal value can be displayed using division (`/`) operator.

Moreover, `round()` function can be used to control the number of decimal places.

```r
# use of `round()` function
var_x <- 5
var_y <- 3

var_div <- var_x / var_y

print(var_div)
print(round(var_div,3))
print(round(var_div,2))
print(round(var_div))
```

produces:

```r
1.666667
1.667
1.67
2
```

`round()` function make rounded integer value of float or decimals.

It will be rounded to `next number` if decimal values are more than `.5` else will be rounded to `previous number`

```r
# use of `round()` function
var_x <- 10.55
var_y <- 10.45

print(round(var_x))
print(round(var_y))
```

produces:

```r
11
10
```

### 2. Relational Operators

The **Relational operators** used to check the relationship between two variables.

+ If the relation is true, it returns logical data type `TRUE`
+ If the relation is false, it returns logical data type `FALSE`

Following table depicts all the Relational Operators in R:

| Operator | Operation | Example  |
| :-------------: |:-------------:| :-----:|
| **`>`** | Greater than | `10 > 5` returns `TRUE` |
| **`<`** | Less than | `10 < 5` returns `FALSE` |
| **`>=`**| Greater than or Equal | `12 >= 10` returns `TRUE`|
| **`<=`**| Less than or Equal | `12 <= 10` returns `FALSE`|
| **`==`**| Equal | `10 == 10` returns `TRUE`|
| **`!=`**| Not Equal | `10 != 10` returns `FALSE`|

#### <u>Use of Relational Operators for two numbers</u>

```r
# use of relational operators for two numbers
var_x <- 24
var_y <- 20

var_gt <- var_x > var_y
var_ls <- var_x < var_y
var_gt_eq <- var_x >= var_y
var_ls_eq <- var_x <= var_y
var_eq <- var_x == var_y
var_nt_eq <- var_x != var_y

sprintf("%d is Greater than %d? - %s", var_x, var_y, var_gt, "\n")
sprintf("%d is Less than %d? - %s", var_x, var_y, var_ls, "\n")
sprintf("%d is Greater than or Equal to %d? - %s", var_x, var_y, var_gt_eq, "\n")
sprintf("%d is Less than or Equal to %d? - %s", var_x, var_y, var_ls_eq, "\n")
sprintf("%d is Equal to %d? - %s", var_x, var_y, var_eq, "\n")
sprintf("%d is Not Equal to %d? - %s", var_x, var_y, var_nt_eq, "\n")
```

produces:

```r
"24 is Greater than 20? - TRUE"
"24 is Less than 20? - FALSE"
"24 is Greater than or Equal to 20? - TRUE"
"24 is Less than or Equal to 20? - FALSE"
"24 is Equal to 20? - FALSE"
"24 is Not Equal to 20? - TRUE"
```

#### <u>Use of relational operators for two vectors</u>
```r
# use of relational operators for two vectors
var_x <- c(2,3.14,10,8)
var_y <- c(4,2.55,14,8)

var_gt <- var_x > var_y
var_ls <- var_x < var_y
var_gt_eq <- var_x >= var_y
var_ls_eq <- var_x <= var_y
var_eq <- var_x == var_y
var_nt_eq <- var_x != var_y

print(var_gt)
print(var_ls)
print(var_gt_eq)
print(var_ls_eq)
print(var_eq)
print(var_nt_eq)
```

produces:

```r
FALSE TRUE FALSE FALSE
TRUE FALSE TRUE FALSE
FALSE TRUE FALSE TRUE
TRUE FALSE TRUE TRUE
FALSE FALSE FALSE TRUE
TRUE TRUE TRUE FALSE
```

### 3. Logical Operators

The **Logical Operators** are used to compare more than one condition.

Following table depicts all the Logical Operators in R:

| Operator | Operation | Example  |
| :-------------: |:-------------:| :-----:|
| **`&`** | **AND** - It returns `TRUE` when both conditions are true | `TRUE & TRUE = TRUE` <br> `TRUE & FALSE = FALSE` <br> `FALSE & FALSE = FALSE` <br> `FALSE & TRUE = FALSE`|
| **&#124;** | **OR** - It returns `TRUE` when one of the condition is true | `TRUE` &#124; `TRUE = TRUE` <br> `TRUE` &#124; `FALSE = TRUE` <br> `FALSE` &#124; `FALSE = FALSE` <br> `FALSE` &#124; `TRUE = TRUE`|
| **`!`**| **NOT** - It returns `FALSE` if condition is true | `!TRUE = FALSE` <br> `!FALSE = TRUE`|


#### <u>Use of AND, OR and NOT operators for numbers</u>

```r
# use of AND operator for numbers
var_x <- 12
var_y <- 17
print(var_x > 5 & var_x < 15)
print(var_y > 5 & var_y < 15)
```
produces:

```r
TRUE
FALSE
```

```r
# use of OR operator for numbers
var_x <- 4
var_y <- 14
print(var_x < 5 | var_x > 15)
print(var_y < 5 | var_y > 15)
```

produces:

```r
TRUE
FALSE
```

```r
# use of NOT operator for numbers
var_x <- 4
print(!var_x < 5)

print(is.numeric(5))
print(!is.numeric(5))
print(is.numeric("Rajesh"))
print(!is.numeric("Rajesh"))
```

produces:

```r
FALSE
TRUE
FALSE
FALSE
TRUE
```

#### <u>Use of AND, OR and NOT operators for vectors</u>

```r
# use of AND operator for vectors
var_x <- c(TRUE, TRUE, FALSE)
var_y <- c(TRUE, FALSE, FALSE)

print(var_x & var_y)
```

produces:

```r
TRUE FALSE FALSE
```

```r
# use of OR operator for vectors
var_x <- c(TRUE, TRUE, FALSE)
var_y <- c(TRUE, FALSE, FALSE)

print(var_x | var_y)
```

produces:

```r
TRUE TRUE FALSE
```

```r
# use of NOT operator for vectors
var_x <- c(TRUE, TRUE, FALSE)

print(!var_x)
```

produces:

```r
FALSE FALSE TRUE
```

> Results of logical operators **&** `vs` **&&** and **&#124;** `vs` **&#124;&#124;** is different. Especially, when used for vectors. <br> **&&** and **&#124;&#124;** operators returns only expression of the first element of vectors.

```r
# use of `&` vs `&&` for vectors
var_x <- c(TRUE, TRUE, FALSE)
var_y <- c(TRUE, FALSE, FALSE)

print(var_x & var_y)
print(var_x && var_y)
```

produces:

```r
TRUE FALSE FALSE
TRUE
```

```r
# use of `|` vs `||` for vectors
var_x <- c(TRUE, TRUE, FALSE)
var_y <- c(TRUE, FALSE, FALSE)

print(var_x | var_y)
print(var_x || var_y)
```

```r
TRUE TRUE FALSE
TRUE
```

### 4. Assignment Operators

The **Assignment Operators** are used to assign a values to variables.

| Operator | Operation | Example  |
| :-------------: |:-------------:| :-----:|
| **`<-`** | Leftwards assignment | `x <- 5` |
| **`<<-`**| Leftwards assignment | `x <<- "Rajesh"` |
| **`->`**| Rightwards assignment | `x -> "Detroja"` |
| **`->>`**| Rightwards assignment | `x ->> 3.14` |
| **`=`**| Leftwards assignment | `x = 2000` |

The operators `<-` and `=` can be used to assign variable in the same environment.

The operator `<<-` is used to assign variables in the parent environments.

#### <u>Use of Assignment Operators</u>
```r
# use of assignment operators
var_x1 <- c(4, TRUE, 2+4i)
var_x2 <<- c(4, TRUE, 2+4i)
c(4, TRUE, 2+4i) -> var_x3
c(4, TRUE, 2+4i) ->> var_x4
var_x5 = c(4, TRUE, 2+4i)

print(var_x1)
print(var_x2)
print(var_x3)
print(var_x4)
print(var_x5)
```

produces:

```r
4+0i 1+0i 2+4i
4+0i 1+0i 2+4i
4+0i 1+0i 2+4i
4+0i 1+0i 2+4i
4+0i 1+0i 2+4i
```

### 5. Miscellaneous Operators

The **Miscellaneous Operators** used for specific purpose.

| Operator | Operation |
| :-------------: |:-------------:|
| **`:`** | **Colon** - Creates the series of numbers in sequence for a vector |
| **`%in%`**| Used to search element in vector |
| **`%*%`**| Used to multiply a matrix with its transpose |

#### <u>Use of Miscellaneous Operators</u>

```r
# use of `:` operator
var_x <- c(2:8)
print(var_x)
```

produces:

```r
2 3 4 5 6 7 8
```

```r
# use of `%in%` operator
var_x <- 4
var_y <- 14
var_z <- 1:10

print(var_x %in% var_z)
print(var_y %in% var_z)
```

produces:

```r
TRUE
FALSE
```

```r
# use of `%*%` operator
var_m = matrix( c(2,6,5,1,10,4), nrow = 2, ncol = 3, byrow = TRUE)
var_t = var_m %*% t(var_m)
print(var_m)
print(var_t)
```

produces:

```r
2 6 5
1 10 4

65 82
82 117
```

#### <u>Download</u>
[`operators.R`](https://github.com/Rajesh-Detroja/R/blob/master/getting_started/operators.R)
