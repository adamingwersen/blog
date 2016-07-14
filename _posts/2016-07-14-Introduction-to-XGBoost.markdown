---
layout:     post
title:      "XGBoost"
subtitle:   "An introduction to Gradient Boosting in R"
date:       2016-07-13
author:     "Adam"
header-img: "img/post-bg-04.jpg"
---

# <center><h2>Introduction to XGBoost</h2></center>
<center><h3>Adam Ingwersen</h3><h4> - Aspiring Data Scientist</h4></center>  
<center>July 10, 2016</center>  
<center><h3> Introduction </h3></center>
The aim of this paper is to self-learn the fundementals of the XGBoost algorithm, how it's implemented in R - and how to apply the package {xgboost} to real data. 

My initial knowledge of XGBoost is quite limited - and as such, this will be a learning-as-writing process. 

Having worked to a very limited extent with supervised learning models and predictive models, this approach may - or may not - prove useful.

<center><h3> What is XGBoost - and how is it commonly applied? </h3></center>

The appreviation, <b>XGBoost</b>, stands for Extreme Gradient Boost. It's basically a type of supervised learning algorithm which penalizes a model for both loss in explanatory power and increases in complexity. Each of these terms are contained in the Objective function, which the alogrithm seeks to optimize given the data. 

<center><h3> Libraries: </center></h3>

```r
pkgs <- c("xgboost",
          "readr",
          "stringr",
          "caret",
          "car")
lapply(pkgs, require, character.only = TRUE)
```

```
## Loading required package: xgboost
```

```
## Loading required package: readr
```

```
## Loading required package: stringr
```

```
## Loading required package: caret
```

```
## Loading required package: lattice
```

```
## Loading required package: ggplot2
```

```
## Loading required package: car
```

```
## [[1]]
## [1] TRUE
## 
## [[2]]
## [1] TRUE
## 
## [[3]]
## [1] TRUE
## 
## [[4]]
## [1] TRUE
## 
## [[5]]
## [1] TRUE
```


<center><h3> Sources: </center></h3>

[AnalyticsVidhya](http://www.analyticsvidhya.com/blog/2016/01/xgboost-algorithm-easy-steps/)
[XGBoost Official Documentation](http://xgboost.readthedocs.io/en/latest/model.html)
[Tianqi Chen - Understanding XGBoost Model on Otto Dataset @ Kaggle](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data)
