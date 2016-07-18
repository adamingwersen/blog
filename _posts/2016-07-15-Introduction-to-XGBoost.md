---
layout:     post
title:      "XGBoost"
subtitle:   "An introduction to Gradient Boosting in R"
date:       2016-07-15
author:     "Adam"
header-img: "img/post-bg-03.jpg"
---
<center><h3> Introduction </h3></center>
The aim of this paper is to self-learn the fundementals of the XGBoost algorithm, how it's implemented in R - and how to apply the package {xgboost} to real data. 

My initial knowledge of XGBoost is quite limited - and as such, this will be a learning-as-writing process. 

Having worked to a very limited extent with supervised learning models and predictive models, this approach may - or may not - prove useful.

<center><h3> What is XGBoost - and how is it commonly applied? </h3></center>

The appreviation, <b>XGBoost</b>, stands for Extreme Gradient Boost. It's basically a type of supervised learning algorithm which penalizes a model for both loss in explanatory power and increases in complexity. Each of these terms are contained in the Objective function, which the alogrithm seeks to optimize given the data. 

<center><h3> Libraries: </h3></center>

{% highlight r %}
pkgs <- c("xgboost",
          "readr",
          "stringr",
          "caret",
          "car",
          "servr",
          "knitr")
lapply(pkgs, require, character.only = TRUE)
{% endhighlight %}



{% highlight text %}
## Loading required package: xgboost
{% endhighlight %}



{% highlight text %}
## Loading required package: readr
{% endhighlight %}



{% highlight text %}
## Loading required package: stringr
{% endhighlight %}



{% highlight text %}
## Loading required package: caret
{% endhighlight %}



{% highlight text %}
## Loading required package: lattice
{% endhighlight %}



{% highlight text %}
## Loading required package: ggplot2
{% endhighlight %}



{% highlight text %}
## Loading required package: car
{% endhighlight %}



{% highlight text %}
## Loading required package: servr
{% endhighlight %}



{% highlight text %}
## Loading required package: knitr
{% endhighlight %}



{% highlight text %}
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
## 
## [[6]]
## [1] TRUE
## 
## [[7]]
## [1] TRUE
{% endhighlight %}


<center><h3> Sources: </h3></center>

[AnalyticsVidhya](http://www.analyticsvidhya.com/blog/2016/01/xgboost-algorithm-easy-steps/)
[XGBoost Official Documentation](http://xgboost.readthedocs.io/en/latest/model.html)
[Tianqi Chen - Understanding XGBoost Model on Otto Dataset @ Kaggle](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data)
