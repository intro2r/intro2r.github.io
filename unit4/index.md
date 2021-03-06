---
layout: default
title: Analyzing Continuous Data
---

# Analyzing Continuous Data

In this unit, you will become familiar with running and plotting correlations and regression in R.

Follow the links to each lecture, lab, and reading.

Scroll down to download the SWIRL lessons.


## Lesson 1. How to test for correlation and causation

Lecture: [Testing associations](../unit4/testing-associations.html)

Learning Goals:
 - Run correlation and simple regression models,
 - Interpret output,
 - Extract and plot details from output.

SWIRL: [Testing_Associations](../unit4/swirl/Testing_Associations.html)

Lab: [Unit 4: Lab 1](../unit4/labs.html)

Reading: Crawley, M. The R Book. Ch 10 Regression.

Functions: `ks.test()`, `cor()`, `lm()`, `abline()`, `coef()`.


## Lesson 2. How to work with multiple predictors

Lecture: [Multiple regression](../unit4/multiple-regression.html)

Learning Goals:
 - Understand how to code different statistical relationships,
 - Interpret model output and diagnose model fit.

SWIRL: [Testing_Associations](../unit4/swirl/Testing_Associations.html)

Lab: [Unit 4: Lab 2](../unit4/labs.html)

Reading: Crawley, M. The R Book. Ch 12. Analysis of Covariance.

Functions: `lm()`


## Lesson 3. How to deal with binomial and count data

Lecture: 

 - [Binomial data](../unit4/binomial-data.html)
 
 - [Count data](../unit4/count-data.html)

Learning Goals:
 - Understand binomial and count data,
 - Know how to analyse and plot these data,
 - Extract, predict, and plot these data.

SWIRL: 

 - [Binomial_Data](../unit4/swirl/Binomial_Data.html)
 
 - [Count_Data](../unit4/swirl/Count_Data.html)
 
Lab: [Unit 4: Lab 3](../unit4/labs.html)

Reading: Crawley, M. The R Book. Chs 13--17.

Functions: `glm()`, `predict()`, `lines()`.


## Lesson 4. How to deal with multiple response variables (multivariate data)

Lecture: [Multivariate Data](../unit4/multivariate-data.html)

Learning Goals:
 - Understand multivariate data,
 - Know how to analyse and plot multivariate data,
 - Search for help on multivariate analyses.
 
More details: 
  - The [vegan](http://vegan.r-forge.r-project.org/),
  - and [labdsv](http://ecology.msu.montana.edu/labdsv/R/labs/) R packages.
  - Material on [ordination](http://cc.oulu.fi/~jarioksa/opetus/metodi/index2016.html),
  - [New lectures](http://cc.oulu.fi/~jarioksa/opetus/metodi/ordination101.html#1) by author of vegan.
  - Manly and Alberto. 2017. [Multivariate statistical methods: A primer](https://www.crcpress.com/Multivariate-Statistical-Methods-A-Primer-Fourth-Edition/Manly-Alberto/p/book/9781498728966). Fourth edition. Taylor & Francis.
  - More examples [here](https://richardlent.github.io/post/multivariate-analysis-with-r/)

SWIRL: [Ordination](../unit4/swirl/Ordination.html)

Lab: [Unit 4: Recap](../unit4/labs.html)

Functions: `pcord`, `prcomp()`, `princomp()`, `pca()`, `biplot()`, `interp()`.
