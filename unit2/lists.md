---
layout: default
title: Lists
---

# Lists

Along with [data frames](../unit2/matices-and-dataframes.html), a list is one of the most useful and most-encountered objects in R.

They are the only object in R that can store different modes of data objects of *different sizes*.

As such, they are the usual output from statistical tests and models, becuase these outputs include single values (e.g., a text statistic or p-value), as well as vectors of confidence limits, and matrices or data frames of input data.

A list is technically a 1-dimensional object.

Lists are akin to a a closet (*wardrobe*), where you can hang multiple different hangers off a single main bar (hence the 1d).

![](http://intro2r.github.io/unit1/img/hangers.jpg)

## How to make a list

Lists are constructed with `list()` (cf. `c()` for atomic vectors).

Notice that, similar to data frames, we can name each component ('hanger') of the list. (For a data frame, we can use a similar construction to name the columns, if we generate the data frame within R).
```r
l <- list(a = 1:4, 
          b = c('i', 'i', 'ii', 'ii'), 
          c = c(1.1, 2.2, 3.3, 4.4)
          )
l
```
```
$a
[1] 1 2 3 4

$b
[1] "i"  "i"  "ii" "ii"

$c
[1] 1.1 2.2 3.3 4.4
```

Here, we have a list of three components, a, b, and c. 

Using `str()` to look at the structure, we can see that we have a list of 3 components: an integer, a character, and a numeric vector.
As usual, we get information on each component, its mode, length, and the first few elements.
```r
str(l)
```
```
List of 3
 $ a: int [1:4] 1 2 3 4
 $ b: chr [1:4] "i" "i" "ii" "ii"
 $ c: num [1:4] 1.1 2.2 3.3 4.4

```

Lists can contain much more than just vectors.
```r
l <- list(a = 1:5, b = list(b1 = 1, b2 = c('one', 'two')), c = data.frame(x = 1:4, y = 5:8, z = 9:12))
l
```
```
$a
[1] 1 2 3 4 5

$b
$b$b1
[1] 1

$b$b2
[1] "one" "two"


$c
  x y  z
1 1 5  9
2 2 6 10
3 3 7 11
4 4 8 12
```

```r
str(l)
```
```
List of 3
 $ a: int [1:5] 1 2 3 4 5
 $ b:List of 2
  ..$ b1: num 1
  ..$ b2: chr [1:2] "one" "two"
 $ c:'data.frame':	4 obs. of  3 variables:
  ..$ x: int [1:4] 1 2 3 4
  ..$ y: int [1:4] 5 6 7 8
  ..$ z: int [1:4] 9 10 11 12
```

## Indexing lists

As described in [Subsetting and Indexing](http://www.intro2r.info/unit2/subsetting-and-indexing.html), we can access various parts of the list using `[`, `[[`, and `$`.
We can access each main component by name (with `$` or `[`), or by number (with `[`).
```r
l$b
```
```
$b1
[1] 1

$b2
[1] "one" "two"
```

Similarly, we can access the sub-lists.
```r
l$b$b2
```
```
[1] "one" "two"
```

And we can directly access the elements using `[[` and `$`.
```r
l$b[['b2']]
```
```
[1] "one" "two"
```

### Accessing list objects

We can use these same tools to access the outputs of statistical models, etc.

For example, the output of a t-test includes the estimates of each mean, t, and p values.
```r
m <- t.test(l$c$x, l$c$y)
m
```
```
	Welch Two Sample t-test

data:  l$c$x and l$c$y
t = -4.3818, df = 6, p-value = 0.004659
alternative hypothesis: true difference in means is not equal to 0
95 percent confidence interval:
 -6.233715 -1.766285
sample estimates:
mean of x mean of y 
      2.5       6.5 
```

Let's look at the structure of this list.
```r
str(m)
```
```
List of 9
 $ statistic  : Named num -4.38
  ..- attr(*, "names")= chr "t"
 $ parameter  : Named num 6
  ..- attr(*, "names")= chr "df"
 $ p.value    : num 0.00466
 $ conf.int   : atomic [1:2] -6.23 -1.77
  ..- attr(*, "conf.level")= num 0.95
 $ estimate   : Named num [1:2] 2.5 6.5
  ..- attr(*, "names")= chr [1:2] "mean of x" "mean of y"
 $ null.value : Named num 0
  ..- attr(*, "names")= chr "difference in means"
 $ alternative: chr "two.sided"
 $ method     : chr "Welch Two Sample t-test"
 $ data.name  : chr "l$c$x and l$c$y"
 - attr(*, "class")= chr "htest"
```

We can extract and display any part of this output.
```r
m$p.value
```
```
[1] 0.004659215
```

We can pass these extracted elements to new objects, which might be tables, figures, ...


- - -

More details in Hadley Wickham's [Advanced R](http://adv-r.had.co.nz/Data-structures.html)

