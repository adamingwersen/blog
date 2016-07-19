---
layout:     post
title:      "Crawling Wikipedia Search Queries"
subtitle:   "Using rvest and RJSONIO packages in R"
date:       2016-07-16
author:     "Adam"
header-img: "img/docubyte-purple.jpg"
tags:		[R Programming | JSON Scraping | Wikipedia | Bitcoin]
---

<h3><center> What are we doing? </center></h3>

The purpose of this tutorial is to show how to obtain time-series data on any Wikipedia.org article of the number of search-queries towards this particular article. As such, this will not show how to crawl different Wikipedia.org pages for content - but rather how to obtain a single, or, if needed, multiple time-series. 

<h3><center> Which tools are we using? </center></h3>

You need a functioning installation of R with the following packages installed:


{% highlight text %}
## Loading required package: rvest
{% endhighlight %}



{% highlight text %}
## Loading required package: xml2
{% endhighlight %}



{% highlight text %}
## Loading required package: dplyr
{% endhighlight %}



{% highlight text %}
## 
## Attaching package: 'dplyr'
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:stats':
## 
##     filter, lag
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
{% endhighlight %}



{% highlight text %}
## Loading required package: plyr
{% endhighlight %}



{% highlight text %}
## --------------------------------------------------------------------
{% endhighlight %}



{% highlight text %}
## You have loaded plyr after dplyr - this is likely to cause problems.
## If you need functions from both plyr and dplyr, please load plyr first, then dplyr:
## library(plyr); library(dplyr)
{% endhighlight %}



{% highlight text %}
## --------------------------------------------------------------------
{% endhighlight %}



{% highlight text %}
## 
## Attaching package: 'plyr'
{% endhighlight %}



{% highlight text %}
## The following objects are masked from 'package:dplyr':
## 
##     arrange, count, desc, failwith, id, mutate, rename,
##     summarise, summarize
{% endhighlight %}



{% highlight text %}
## Loading required package: stringr
{% endhighlight %}



{% highlight text %}
## Loading required package: RJSONIO
{% endhighlight %}



{% highlight text %}
## Loading required package: ggthemes
{% endhighlight %}



{% highlight text %}
## Warning in library(package, lib.loc = lib.loc, character.only = TRUE,
## logical.return = TRUE, : there is no package called 'ggthemes'
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
## [1] FALSE
{% endhighlight %}

<h3><center> Step One: Create Links </center></h3>

On [this website](http://stats.grok.se/en), there are some graphs on any and all Wikipedia Articles - we are interested in the complete dataset behind one of the 3-monthly time-series presented [here](http://stats.grok.se/en/201601/Bitcoin). I can see a bar-chart for 3 months at a time - but I would like to see a bigger picture...

The solution is to look into the HTML of the website. All the possible dates are contained within a single css.selector. And given the structure of the link, we can do the following:


{% highlight text %}
## Error in eval(expr, envir, enclos): could not find function "kable"
{% endhighlight %}

Some dates contain a space at the beginning or end of string, we can fix that by "trimming" the strings:


Now, we can create links for the crawler. We simply want to iterate over all possible dates in the link while keeping the search-term constant. Given that I'm currently interested in Bitcoins, I set my search-term accordingly:



{% highlight text %}
## Error in eval(expr, envir, enclos): could not find function "kable"
{% endhighlight %}

Now we have a list of viable links. 

<h3><center> Step Two: Deploy crawler </center></h3>

The content on groks.se is formatted as a JSON table. This requires some extra work as the content is nested. Luckily, there's an R-package for that: RJSONIO


{% highlight text %}
## Error in eval(expr, envir, enclos): could not find function "kable"
{% endhighlight %}

You now have a dataframe consisting of two columns with a daily search-query count on any Wikipedia Article. 

<h3><center> What do I use it for? </center></h3>

I used this particular data to do a cointegration analysis alongside Google-Trends data and Real Bitcoin Price/Trade Volume data. For illustration purposes, here's a plot:


{% highlight text %}
## Error in eval(expr, envir, enclos): could not find function "theme_economist"
{% endhighlight %}

![plot of chunk plot](/blogfigure/source/2016-07-19-Wikipedia-Search/plot-1.png)
