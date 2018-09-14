---
layout: default
title: Matrices and Dataframes
---

# Matrices and Dataframes

Both are two-dimensional data structures.

Matrices are atomic vectors with dimensions and can only have one mode (type) of data.

Dataframes can have columns of different data modes.


# Matrices

Matrices are an extension of numeric or character vectors. 

They are not a separate type of object but simply an atomic vector with dimensions; the number of rows and columns.

Because they are an atomic vector, all the elements are the same type (integer, or numeric, or, etc).

Matrices are used frequently in mathematical models and statistics.


## How to make a matrix

We can create an empty matrix and fill it later,
```{r}
matrix(ncol = 2, nrow = 2)
```

```
     [,1] [,2]
[1,]   NA   NA
[2,]   NA   NA
```

or create one from vector
```r
matrix(1:4, ncol = 2, nrow = 2)
```
```
     [,1] [,2]
[1,]    1    3
[2,]    2    4
```

By default, matrices are filled by columns. We can fill be rows instead.
```r
matrix(1:4, ncol = 2, nrow = 2, byrow = TRUE)
```
```
     [,1] [,2]
[1,]    1    2
[2,]    3    4
```

## How to label a matrix

We can label the columns ...
```r
m <- matrix(1:4, ncol = 2, nrow = 2)
colnames(m) <- c("A", "B")
m
```
```
     A B
[1,] 1 3
[2,] 2 4
```

... and the rows
```r
rownames(m) <- c("a", "b")
m
```
```
  A B
a 1 3
b 2 4
```

## How to add to a matrix

We can add extra columns
```r
cbind(m, 5:6)
```
```
  A B  
a 1 3 5
b 2 4 6
```

or rows
```r
rbind(m, 7:8)
```
```
  A B
a 1 3
b 2 4
  7 8
```


- - -

# Dataframes

Dataframes are also two-dimensional objects. But, unlike matrices, dataframes can include columns of any data type.

Techically, data frames are a type of list where every part (i.e., column) of the list has same length. A data frame is therefore a rectangular list.

Data frames area akin to the usual "observations and variables" model that most statistical software uses. They are also similar to database tables. 

So, each row of a data frame should represent an observation and the elements in a given row represent information about that observation. Each column has all the information about a particular variable for the entire data set.

Dataframes are most likely what you will use to work with your own data.

Each column can only be one mode or data type.

Each column is the same length.


## How to make a dataframe

Can be created with `data.frame()`. This works ok for small datasets.
```r
df <- data.frame(sample_id = c('i', 'ii', 'iii', 'iv'), value = c(1,2,3,4))
df
```
```
  sample_id value
1         i     1
2        ii     2
3       iii     3
4        iv     4
```

For larger dataset, more usually you will read in external data using `read.table()` or `read.csv()` (See [Importing Data](http://www.intro2r.info/unit2/importing-data.html))


## How to label a dataframe

We can label the columns with `colnames()`...
```r
colnames(df) <- c('col1', 'col2')
df
```
```
  col1 col2
1    i    1
2   ii    2
3  iii    3
4   iv    4
```

... and the rows with `rownames()`
```r
rownames(df) <- c('row1', 'row2', 'row3', 'row4')
df
```
```
     col1 col2
row1    i    1
row2   ii    2
row3  iii    3
row4   iv    4
```

## How to add to a dataframe

We can add columns using `cbind()` and rows using `rbind()`, as for matrices.
```r
col3 <- c(5,6,7,8)
cbind(df, col3)
```
```
     col1 col2 col3
row1    i    1    5
row2   ii    2    6
row3  iii    3    7
row4   iv    4    8
```

We can also create new columns using the `$` and new column name. 
```r
df$col4 <- c(9, 10, 11, 12)
df
```
```
     col1 col2 col4
row1    i    1    9
row2   ii    2   10
row3  iii    3   11
row4   iv    4   12
```

## Examining dataframes and matrices

We can check if it is a dataframe, with `is.data.frame()`
```r
is.data.frame(df)
```
```
[1] TRUE
```

And confirm that is it, actually, a list.
```r
is.list(df)
```
```
[1] TRUE
```


We can check the dimenions with `dim()`
```r
dim(df)
```
```
4 3
```

And ask how many columns with `ncol()`
```r
ncol(df)
```
```
[1] 3
```

and rows with nrow()
```r
nrow(df)
```
```
[1] 4
```


We can check the structure, with `str()`
```r
str(df)
```
```
'data.frame':	4 obs. of  3 variables:
 $ col1: Factor w/ 4 levels "i","ii","iii",..: 1 2 3 4
 $ col2: num  1 2 3 4
 $ col4: num  9 10 11 12
```

We can examine the first few rows with `head()`
```r
head(df)
```
```
     col1 col2 col4
row1    i    1    9
row2   ii    2   10
row3  iii    3   11
row4   iv    4   12
```

And the last few rows with `tail()`
```r
tail(df)
```
```
     col1 col2 col4
row1    i    1    9
row2   ii    2   10
row3  iii    3   11
row4   iv    4   12
```
