---
id: comments
title: Comments
---

## What is Comments in R?

Comments helps R interpreter to ignore the statement(s) while executing R program.

## How to Write a Comment in R?

**Single-line comment** is written using `#` in the beginning of the statement as follows:

```r
# My first program in R Programming

my_string <- "Hello, World!"
print (my_string)
```

produces:

```r
"Hello, World!"
```

R does not support **multi-line comments** but can be performed by a trick as follows:

```r
# My first program in R Programming

my_string <- "Hello, World!"
print (my_string)

if(FALSE) {
  "This is a first line!
   This is a second line!
  "
}
```

produces:

```r
"Hello, World!"
```

#### <u>Download</u>
[`comments.R`](https://github.com/Rajesh-Detroja/R/blob/master/getting_started/comments.R)
