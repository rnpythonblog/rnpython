---
title: R Prevalence in India
subtitle: "A comparison of R and Python prevalence in India"
author: Manohar Mulchandani
date: '2021-01-18'
categories: []
tags:
  - R
  - Python
  - India
keywords:
  - tech
summary: "How does R fare vis-a-vis Python in India? We explore this question using data from Kaggle Machine Learning and Data Science Survey 2020: we also use data from past surveys in 2018 and 2019, to explore trends. The analysis seems to suggest that those respondents who program both in R as well as Python seem to better leverage the data science tools in R ecosystem"
---

<style>
body {
    background-color:cornsilk;
}
</style>

## Introduction
This blog post explores the prevalence and use of R in India. The exploration is based on the global [*Kaggle Machine Learning and Data Science Survey 2020*](https://www.kaggle.com/c/kaggle-survey-2020) (KMLDSS 2020) conducted in October 2020. [Kaggle](https://www.kaggle.com) is an online community of data scientists and machine learning practitioners. The survey data contains responses from 20036 data scientists and machine learning practitioners from 55 countries. An [executive summary](https://www.kaggle.com/kaggle-survey-2020) is available on the Kaggle website.








The post is organized in three parts:

1. We first contextualize the Data Science practice in India within the global scenario, focusing on R and Python.
2. We then compare the prevalence of R and Python among Data Science professionals in India.
3. We finally deep dive into how R is used by Data Science professionals in India.

In general, we will be working with the [2020](https://www.kaggle.com/c/kaggle-survey-2020) survey data. However, at places, it is insightful to look at data from past Kaggle MLDSS surveys, especially to study trends. We will use survey data from [2018](https://www.kaggle.com/kaggle/kaggle-survey-2018) and [2019](https://www.kaggle.com/c/kaggle-survey-2019).

A companion [Shiny app](https://rnpython.shinyapps.io/kaggle_mldss_2020/) enables a similar exploration for Top 10 countries (in terms of number of respondents), by reproducing all the plots in this blog post.

## Part I: India in the Global Context
The chart below shows the Top 10 countries in terms of number of respondents.
<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-3-1.png" width="70%" style="float:right; padding:20px" />
- India has the most respondents at **29.2%**
- USA has the second highest respondents at **11.2%**.
- The Top 10 countries represent over half of the respondents.

Since R and Python are the two most popular languages used by data scientists and machine learning practitioners, its instructive to see how the Top 10 countries fare in terms of R versus Python prevalence.

The bar graph below shows that the number of Python respondents is much higher than R.
<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-4-1.png" width="70%" style="float:right; padding:20px" />


- Python percentages vary within a narrow range of [77% - 83%]
- R percentages vary in a wide range: [8% - 32%]. 

As far as R is concerned, India is somewhere in the middle of this range at **17%**, while Spain tops the list with **37%** of its respondents using R.

**Note that some of the respondents program in Python as well as R. So the total percentages for a country may add up to more than 100%.**


### Programming Language Choices
Even though R and Python are considered the top two preferred programming languages for data science and machine learning practitioners, the survey respondents use other languages too. While one would expect to see R and Python as the top 2 languages of the respondents, the reality is quite different.

The bar graph on the left below shows that, globally, most of the respondents program in Python, followed by SQL. R is at the 3rd spot (not quite at #2, as we would expect it to be). As for India, R is at the 6th spot. SQL retains its second spot in all the Top 10 countries, as can be seen from the companion Shiny app.


<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-5-1.png" width="1536" />


### R and Python 
We now switch focus to just R and Python. 

Earlier, in the context of Top10 countries, we saw the relative percentages of respondents who program in R and Python. Some of those respondents use both R and Python. To highlight real differences between R and Python respondents, the subsequent analysis will split the respondents into the following three categories:

1. Those who program only in Python
2. Those that program only in R
3. Those that program in Python as well as R (Python + R)

We ignore respondents who do not program in R or Python, since our focus is on R and Python.

The plots below show relative percentages of respondents in these three categories in India and compare them with global percentages.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-6-1.png" width="1536" />

**Note that the total does not add up to 100, since we ignore respondents who do not program in either R or Python**.

In India about 17% (15% + 2%) of the respondents program in R versus 22 (18% + 4%) globally.

On the other hand, 81% (66% + 15%) of respondents based in India program in Python as compared to 78% globally.

As a comparison, 32% of the respondents from US program in R, of which 7% program in R only, as can be seen in the companion Shiny app.

At the global level, the percentage of respondents programming in R is less compared to Python. The numbers in India are even smaller. R clearly lags Python when it comes to respondents from India. Since the respondents do not form a randomized sample, we cannot say for sure that R adoption lags behind that of Python. But the difference between the two is too large to not consider the possibility that R adoption lags that of Python by a significant amount.

This sets the stage for Part 2.

## Part II: R and Python over the years in India
We begin by looking at trends over the last three years in terms of percentage of respondents who use R and Python.


<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-7-1.png" width="1344" />

The plots show a gradual rise in the number of respondents who program in Python. As for R, the the number of respondents dipped from 190 (4.3%) in 2018 to 108 (2.3%) in 2019 and dipped a bit further in 2020. There is an overall reduction in those that program in R, since the percentage of respondents who program in both R and Python has also gone down from 2018 to 2020.

If we look at the US respondents in the companion Shiny app, we see a similar trend. However, the growth in percentage of respondents programming in Python is gradual (from 66% in 2018 to 76% in 2020); for R, the reduction goes from 8% in 2018 to 7% in 2020.

### Exploring the dip in R respondents
To investigate the dip in respondents who program in R, let's explore the **Job Titles** reported by respondents to see if there is a change in the respondent profile over the years.

There are some differences in the way data about job titles was collected across the years. For example, 

- The title **Machine Learning Engineer** was introduced in 2020.
- Year 2018 had quite a lot of titles that were dropped in 2019 and 2020.

We retain only the list of common titles, with the exception of **Machine Learning Engineer**. The titles that we drop from 2018 had very few respondents. On the other hand, those reporting a title of **Machine Learning Engineer** is not an insignificant number. Besides, this is something we will see in future surveys, so it makes sense to retain it.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-8-1.png" width="1344" />

We have organized the plot so that the titles reported by respondents who program on in **R only** are on the left side of the plot.

The most common titles reported by **R only** Programmers are Data Analyst, Business Analyst and Data Scientist: we also see dip in the number of respondents for these titles. In contrast, we notice a small uptick in the numbers of Statisticians, but this rise in Statistician numbers is not enough to cover the dip in Business Analysts and Data Analysts.

We also see a dip in the numbers for these titles for those that program in both **R and Python**.

As for those programming in **Python only**, we see that the numbers of Business Analysts, Data Analysts and Data Scientists going up.

Let's look at the tasks performed by Business Analysts, Data Analysts and Data Scientists to see if there is a difference between those who program in R and those who program on Python.

We first look at data from 2018 since there was a sizeable response in that year from respondents who use R.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-9-1.png" width="672" />

Clearly, the tasks performed by Business Analysts and Data Analysts are similar, regardless of the progamming language choice. In fact, most of them "Analyze and understand data".

And now, let's see the data for 2020.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-10-1.png" width="672" />

Comparing the plots from 2018 and 2020, we see a significant dip in those that program in R only. We see a small dip for those that program in R and Python. However, we see an increase for those who program in Python, in 2020. 

> Either, Business Analysts and Data Analysts programming in R are not participating in numbers compared to previous years leading to the dip.

> Or perhaps, there are fewer active Business Analysts and Data Analysts programming in R. If so, is there an underlying reason?

Let's check on compensation numbers for R Programmers vis-a-vis Python programmers to see if there is not enough incentive to program in R.

#### Comparing Compensation for R and Python Programmers

The following chart shows the percentage of respondents in different compensation levels, across all titles. Respondents using R are represented well in all compensation levels.

For example, for 4% of all respondents who use R, the compensation is between $7,500 - $9,999, There are very few respondents at the very high compensation levels and there is R representation in those as well.

**The percentages do not add upto 100% for each language, since some of the respondents have not provided the data.**

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-11-1.png" width="1152" />


Let's look at compensation only for Business and Data Analysts

From the chart, it appears that Business and Data Analysts do not figure at the higher compensation levels.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-12-1.png" width="1152" />

Perhaps, compensation is a factor.

The dip in number of respondents that program in R, over the years, can be directly attributed to fewer respondents in the Business Analyst and Data Analyst roles However, we do not see a dip in response from those with these titles but programming in Python.

There is a large number of tools in the R eco-system for tasks performed by Business Analysts and Data Analysts, not to mention that it is generally easy to start with R. The packages in the **`tidyverse`** universe make it relatively easy to perform data analysis and create powerful visualizations. *All the analysis and plots in this blog post were created using R using the **`tidyverse`** packages*. Besides, the **`shiny`** package makes it easy to create Web Apps and share analysis on the web without requiring knowledge of web programming. There is strong community support, and for those looking to do more, there are a large number of packages for Machine Learning in R. 

If the lower number of R respondents are representative of the overall numbers of R programmers in India, it would be worth investigating the reasons.

> Additional surveys regarding attitude towards R may help shed more light on this.

We will now deep dive into the use of R, to better understand how R is being used in India.

## Part III: R Usage in India

In our analysis, while our focus is on respondents who program in R only, we include those respondents who program in both R and Python to see if there are any similarities.

We begin by exploring the tools and libraries used by respondents who use R.

### Visualization Tools
Effective visualizations are important for data science teams.

The following plot shows the Visualization tools employed by respondents who use R: we are primarily interested in seeing the use of [**ggplot**]((https://ggplot2.tidyverse.org/)) and [**shiny**](https://shiny.rstudio.com/).

The percentages are computed as a fraction of respondents for the specified language. For example, 67% of repondents who use R, use Ggplot/ggplot2.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-13-1.png" width="1344" />

The findings are as expected. Those that program in R use more [**`ggplot`**](https://ggplot2.tidyverse.org/) and [**`shiny`**](https://shiny.rstudio.com/), while those who program in Python + R use more of **`Matplotlib`** and **`Seaborn`**. A comparable number of those who program in both R and Python, also use **`ggplot`** and **`shiny`**.

Around 2/3rd of R respondents use **`ggplot`**. While the number is impressive, one would expect a higher number.

And when it comes to **`shiny`**, only 20% of R respondents use it. Given the popularity of Shiny, this is very low.

Let's see if there is a differences in use of **`ggplot`** and **`Shiny`** across titles for **R Programmers**. 
We will actually plot the numbers instead of percentages, since percentages can hide the true picture, when the number of respondents is low.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-14-1.png" width="1536" />

As we saw before, 67% of R respondents use `ggplot`. However, the number of respondents is quite low: 5 Business Analysts and 11 Data Analysts. The numbers for `shiny` are smaller. If we look at those that program in both R and Python, we see higher numbers for `ggplot` and `shiny`. The higher numbers for those that program in R and Python may be a reflection of the total number of respondents in the two categories: the number of respondents who program in both R and Python is 873, while those who program only in R is 101.

### Machine Learning Libraries and Algorithms

The plot below shows the different Machine Learning libraries used by R Programmers. On the left are ML related libraries most used by those respondents who program in R. We see that `caret` is the most popular R package, with 19% of R respondents using it.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-15-1.png" width="1344" />

Clearly, R Programmers employ a large number of popular Machine Learning libraries. It is no surprise to see [caret](https://cran.r-project.org/web/packages/caret/vignettes/caret.html) package scoring the highest for R only respondents. It will be interesting to watch for [tidymodels](https://www.tidymodels.org/) next year.

Let's explore usage of these ML Libraries across job titles. As with the visualization libraries, there are more users of `caret` and `tidymodels` among those who program in both R and Python, and likely for the same reason.


<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-16-1.png" width="1536" />

Finally, let look at the ML Algorithms employed by R Programmers.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-17-1.png" width="1536" />

Again, R respondents employ a wide variety of Machine Learning algorithms. Linear Regression seems to be the most popular machine learning algorithm used. Indeed, as per the executive summary referred to at the beginning of this post, Linear Regression is the most popular method among Data Scientists, so this does not come as a surprise.

## Closing Notes
Clearly, the prevalence of R in India lags Python by a large number. However, it looks like respondents who use both R and Python do leverage the R eco-system.

In other words, to understand the level of R prevalence in India, we need to look at data science practitioners who use both R and Python, rather than those who just program in R. 

There is room for improving the use of R in India and there is a good eco-system to leverage. Perhaps these need to be re-introduced to the community in India.

*This blog post was created using RMarkdown and rendered using the R package `blogdown`. The analysis and plots employed several [tidyverse](https://www.tidyverse.org) packages. The RMarkdown document can be accessed on [GitHub](https://github.com/rnpythonblog/rnpython/blob/main/content/post/2021-01-18-r-prevalence-in-india/index.en.Rmarkdown)*.
