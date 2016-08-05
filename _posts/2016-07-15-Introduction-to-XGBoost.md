---
layout:     post
title:      "XGBoost"
subtitle:   "An introduction to Gradient Boosting in R"
date:       2016-07-15
author:     "Adam"
header-img: "img/docubyte-blue.jpg"
tags:		[R Programming | Machine Learning]
---
<center><h3> Introduction </h3></center>
<hr>

The aim of this paper is to self-learn the fundementals of the XGBoost algorithm, how it's implemented in R - and how to apply the package {xgboost} to real data. 

My initial knowledge of XGBoost is quite limited - and as such, this will be a learning-as-writing process. 

Having worked to a very limited extent with supervised learning models and predictive models, this approach may - or may not - prove useful.

<center><h3> What is XGBoost - and how is it commonly applied? </h3></center>
<hr>

The abbreviation, <b>XGBoost</b>, stands for Extreme Gradient Boost. It's basically a type of supervised learning algorithm which penalizes a model for both loss in explanatory power and increases in complexity. Each of these terms are contained in the Objective function, which the alogrithm seeks to optimize given the data. 

The XGBoost has been implemented effficiently in R within the `xgboost` package. The framework can be scaled and has been used in winning multiple [Kaggle](https://kaggle.com) competitions
.
<center><h3> Which concepts do I need to understand before delving into Extreme Gradient Boosting? </h3></center>
<hr>


<center><h3> The theory of XGBoost </h3></center>
<hr>

<center><h3> How to apply the algorithm to real-life data in R </h3></center>
<hr>

<center><h4> Libraries: </h4></center>
<hr>


{% highlight r %}
pkgs <- c("xgboost",
          "readr",
          "stringr",
          "caret",
          "car",
          "servr",
          "knitr")
{% endhighlight %}


{% highlight r %}
lapply(pkgs, require, character.only = TRUE)
{% endhighlight %}

<center><h3> How to gain insigths from the output </h3></center>
<hr>



<center><h3> Sources: </h3></center>
<hr>

[AnalyticsVidhya](http://www.analyticsvidhya.com/blog/2016/01/xgboost-algorithm-easy-steps/)
[XGBoost Official Documentation](http://xgboost.readthedocs.io/en/latest/model.html)
[Tianqi Chen - Understanding XGBoost Model on Otto Dataset @ Kaggle](https://www.kaggle.com/tqchen/otto-group-product-classification-challenge/understanding-xgboost-model-on-otto-data)
