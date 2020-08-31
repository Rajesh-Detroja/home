---
id: data-types
title: Data Types
---

## What is the Data Types in R?

> In the R programming, The **variables** are assigned with **R-Objects** and the **data type of the R-object** becomes the **data type of the variable**.

There are many types of **R-objects**. The frequently used ones are −

+ Vectors
+ Lists
+ Matrices
+ Arrays
+ Factors
+ Data Frames

The most basic type of **R-objects** is a **vector** object.

> A **vector** object can only contain **data type of the same class**. Except, ***List***.

Empty vector can be created with the `vector()` function.

```r
# creating a empty with `vector()` function
var_vec <- vector()
print(var_vec)
```

produces:

```r
logical(0)
```

Here, `var_vec` is a **variable** and `vector()` is a function to create a **vector** object.

The results `logical(0)` means the vector is empty without any values stored inside.

## How many Data Types there in R?

There are **6** basic **data types** or **atomic classes** of objects:

### **1. Numeric**

The most common data type in R is **numeric**. A variable or numeric series with or without decimals can be stored as numeric data.

<u>**Numeric series without decimals**</u>

```r
# numeric series without decimals
var_x <- c(2,6,8)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2 6 8
"numeric"
```

<u>**Numeric series with decimals**</u>

```r
# numeric series with decimals
var_x <- c(2.2, 6.4, 8.6)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2.2 6.4 8.6
"numeric"
```

> The `c()` function can be used to **create vectors** of objects by concatenating things together.

### **2. Integer**

An **integer** data types is a special case of numeric data. A variable or numeric series without decimals will be stored as integer data.

Integer variable can be created with function `as.integer()`

<u>**Creating an integer variable** </u>
```r
# creating integer variable
var_x <- as.integer(2)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2
"integer"
```

<u>**Creating an integer variable by appending an L suffix**</u>

```r
# creating an integer variable by appending an L suffix
var_x <- 2L
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2
"integer"
```

> If you explicitly want an **integer**, you need to specify the **L suffix**. So entering **1** in **R** gives you a **numeric** object; entering **1L** explicitly gives you an **integer** object.

<u>**Coerce a numeric decimals value into an integer variable**</u>

```r
# coerce a numeric decimals value into an integer variable
var_x <- as.integer(2.5)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2
"integer"
```

<u>**Coerce a string of decimal value into an integer variable**</u>

```r
# coerce a string of decimal value into an integer variable
var_x <- as.integer("2.5")
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
2
"integer"
```

<u>**Coerce a string of non-decimal value into an integer variable**</u>
```r
# coerce a string of non-decimal value into an integer variable
var_x <- as.integer("Rajesh")
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
Warning message:
NAs introduced by coercion
NA
"integer"
```

<u>**Logical values into an integer variable**</u>
```r
# Logical values into an integer variable
var_x <- as.integer(TRUE)
print(var_x)

var_y <- as.integer(FALSE)
print(var_y)

# checking data type of variable with "class" function
class(var_x)
class(var_y)
```

produces:

```r
1
0
"integer"
"integer"
```

### **3. Complex**

**Complex** data types in R is defined by an imaginary number, or i.

<u>**Creating an complex variable**</u>

```r
# creating an complex variable
var_x <- 1 + 0i
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
1+0i
"complex"
```

<u>**Creating an complex variable with `c()` function**</u>

```r
# creating an complex variable with `c()` function
var_x <- c(1+0i, 2+4i)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
1+0i 2+4i
"complex"
```

### **4. Character**

The data type **character** is used when storing **string** or **text** by using `""`

<u>**Creating an character variable**</u>

```r
# creating an character variable
var_x <- "This is a string"
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
"This is a string"
"character"
```

<u>**Everything inside `""` will be considered as character**</u>

```r
# everything inside `""` will be considered as character
var_x <- c("3.14")
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
"3.14"
"character"
```

<u>**Character + Numbers produces a whole character variable**</u>

```r
# character + numbers produces a whole character variable
var_x <- c("string", 2, 3.14, 6)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
"string" "2" "3.14" "6"
"character"
```

<u>**Space within `""` makes a different character variable**</u>

```r
# space within `""` makes a different character variable
var_x <- "string "
var_y <- "string"

# `char_var_space` is equal to `char_var_no_space`?
var_x == var_y
```

produces:

```r
FALSE
```

<u>**Creating a character variable with `as.character()` function**</u>

```r
# creating a character variable with `as.character()` function
var_x <- as.character(3.14)
print(var_x)

# checking data type of variable with "class" function
class(var_x)
```

produces:

```r
"3.14"
"character"
```

<u>**Two character variables can be concatenated with the `paste()` function**</u>

```r
# two character variables can be concatenated with the `paste()` function
var_x <- "Rajesh"
var_y <- "Detroja"

paste(var_x, var_y)
```

produces:

```r
"Rajesh Detroja"
```

<u>**Creating a character variable with `sprintf()` function**</u>

```r
# creating a character variable with `sprintf()` function
var_x <- sprintf("Computer of %s has %dTb of space!", "Rajesh", 1)
print(var_x)
```

produces:

```r
"Computer of Rajesh has 1Tb of space!"
```

<u>**Applying a `substr()` function on character variable to extract sub-string**</u>

```r
# applying a `substr()` function on character variable to extract sub-string
var_x <- substr("I am Rajesh Detroja!", start=6, stop=19)
print(var_x)
```

produces:

```r
"Rajesh Detroja"
```

<u>**Replacing first occurrence of word "Detroja" with "Patel" by using 'sub()' function**</u>

```r
# replacing first occurrence of word "Detroja" with "Patel" by using 'sub()' function
var_x <- "I am Rajesh Detroja"
sub("Detroja","Patel", var_x)
```

produces:

```r
"I am Rajesh Patel"
```

### **5. Logical**

A **logical** data type is a data type with only two values; `TRUE` or `FALSE`

<u>**Creating a logical variable**</u>

```r
# creating a logical variable
var_x <- TRUE
var_y <- FALSE

print(var_x)
print(var_y)

# checking data type of variable with "class" function
class(var_x)
class(var_y)
```

produces:

```r
TRUE
FALSE
"logical"
"logical"
```

<u>**Comparing numeric variable**</u>

```r
# comparing numeric variable
var_x <- 10
var_y <- 20
var_z <- 30

# is `var_x` and `var_y` is equal?
var_x == var_y

## is `var_z - var_y` is equal to `var_x`
(var_z - var_y) == var_x
```

produces:

```r
FALSE
TRUE
```

### **6. Raw**

There is also [**raw**](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/raw) data type in R, but they are not commonly used directly in data analysis.

<u>**Converting character variable to raw**</u>

```r
# converting character variable to raw
var_x <- "Rajesh"
charToRaw(var_x)
```

produces:

```r
52 61 6a 65 73 68
```

### Summary

| Data Type | Example           | Description  |
| :-------------: |:-------------:| :-----:|
| Numeric | 2, 6.4, 100 | Numbers of all kinds |
| Integer | 2, 4L, 200L     | Explicitly Integers |
| Complex | 2+4i | Real Value + Complex Value |
| Character | ‘R’, “Rajesh”      | Characters and Strings |
| Logical | TRUE, FALSE | Boolean Values |
| Raw | 52 - 61 - 6a - 65 - 73 - 68 | Any data is stored as raw bytes |

#### <u>Download</u>

[`data_types.R`](https://github.com/Rajesh-Detroja/R/blob/master/getting_started/data_types.R)
