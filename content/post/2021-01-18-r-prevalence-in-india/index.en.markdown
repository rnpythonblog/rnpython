---
title: R Prevalence in India
author: Manohar Mulchandani
date: '2021-01-18'
categories: []
tags:
  - R
  - Python
  - India
keywords:
  - tech
summary: "How does R fare vis-a-vis Python in India. This post explores this question by using data from Kaggle MLDSS Survery 2020."
subtitle: "How does R fare vis-a-vis Python in India"
---

<style>
body {
    background-color:cornsilk;
}
</style>

## Introduction
This blog post analyzes the prevalence and use of R in India. The analysis is based on the global Kaggle Machine Learning and Data Science Survey 2020 (KMLDSS 2020) conducted in October 2020. [Kaggle](https://www.kaggle.com) is an online community of data scientists and machine learning practitioners. The survey data contains responses from 20036 data scientists and machine learning practitioners from 55 countries. An [executive summary](https://www.kaggle.com/kaggle-survey-2020) is available on the Kaggle website.








The analysis is organized in three parts:

1. We first contextualize the Data Science practice in India within the global scenario, vis-a-vis R and Python.
2. We then compare the prevalence of R and Python among Data Science professionals in India.
3. We finally deep dive into the practice of R in India.

In general, we will be working with the 2020 survey data. However, at places, it is insightful to look at data from past Kaggle MLDSS surveys, especially to study trends. We will use survey data from 2018 and 2019.

A companion [Shiny app](https://manohar.shinyapps.io/kaggle_mldss/) enables a similar analysis for Top10 countries (in terms of number of respondents), by reproducing all the plots in this blog post.

## Part I: India in the Global Context
The two charts below illustrate participation in the survey by data science and machine learning professions residing in India, within the global context.

The bar graph on the left shows the Top 10 countries with most number of respondents (in percentage terms). The size of the bars in the graph is proportional to the percentage of respondents from that country. India has the maximum number of respondents at 29.2% followed by United States at 11.2%. Together, the Top 10 countries represent over half of the respondents.

Since R and Python are the two most popular languages used by data scientists and machine learning practitioners, its instructive to see how the Top 10 countries fare in terms of R versus Python prevalence.

We compare the percentage of respondents for R and Python and as we can see from the chart on the right, Python percentages vary within a narrow range of 77% - 83%, but the R percentages vary in a wide range: 8% - 32%. As far as R is concerned, India is somewhere in the middle of this range, while USA tops the list with 32% of its respondents using R.

**Note that some of the respondents program in Python as well as R. So the total percentages for a country may add up to more than 100%.**

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-3-1.png" width="1536" />

### Programming Language Choices
Even though R and Python are considered the top programming languages for data science and machine learning practitioners, the survey respondents come from a wide variety of backgrounds and use multiple languages. Thus, while one would expect to see R and Python as the top 2 languages of the respondents, the reality is quite different.

The bar graph on the left below shows that, globally, Python is the top choice and R is at the 3rd spot (not quite at #2, as we would expect it to be.) The results for India are even more surprising: R drops to the 6th spot.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-4-1.png" width="1536" />

### R and Python 
We now switch focus to just R and Python. 

Earlier, in the context of Top10 countries, we saw the relative percentages of respondents who program in R versus Python. Some of those programmers use both R and Python. To highlight real differences between the Python and R programmers, the subsequent analysis will split the respondents into the following three types:

1. Those who program only in Python
2. Those that program only in R
3. Those that program in Python as well as R (Python_n_R)

We ignore respondents that do not program in R or Python.

The plots below show relative percentages of these three types of respondents in India and compare them with global percentages.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-5-1.png" width="1536" />

**Note that the total does not add up to 100, since we ignore respondents who do not program in either R or Python**.

In India about 17% (15% + 2%) of the respondents program in R versus 22 (18% + 4%) globally.

On the other hand, 81% (66% + 15%) of respondents based in India program in Python as compared to 78% globally.

At the global level, the percentage of respondents programming in R is less compared to Python. The numbers in India are even smaller. R clearly lags Python when it comes to respondents from India. Since the respondents do not form a randomized sample, we cannot say for sure that R adoption lags behind that of Python. But the difference between the two is too large to not consider the possibility that R adoption lags that of Python by a significant amount.

This sets the stage for Part 2.

## Part II: R and Python over the years in India
We begin by looking at trends over the last three years in terms of percentage of respondents who use R and Python.


<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-6-1.png" width="1344" />

From the plots above, we see a big growth for Python from 2019 to 2020, while R dips from 2018 to 2019 and dips a wee bit further in 2020. We will try and explore the dip in R respondents through the years.

### Exploring the dip: changes in respondent profile over the years
To investigate what has caused the dip in respondents who program in R, we will explore **Educational Background** and **Job Titles** reported by respondents to see if there is a change in the respondent profile over the years.


#### Educational Background 

We ignore the following respondents who have not specified their educational background clearly:                                  
  1. I prefer not to answer                                                 
  2. No formal education past high school                                            
  3. Some college/university study without earning a bachelor’s degree

These numbers are very small (< 5%) and do not impact our analysis. Besides the plots are less cluttered.

**We plot the actual numbers instead of percentages.**

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-7-1.png" width="1536" />

We notice a dramatic shift in the educational background of respondents programming in **R only**: there is a big dip in the number of respondents with Bachelor's degree from 2018 to 2019 and this dip continues to 2020. There is also a dip in the number of respondents with Master's degree.  We do not see such a shift for those that program in **Python only**. There is a  dip for those that program in **both Python and R** in 2019 and some of that ground is recovered in 2020.


#### Overall Educational Profile Trends in India
Let's explore the educational background over the years for all respondents from India to see if there is a general fall in number of respondents with Bachelor's and Master's degree.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-8-1.png" width="1344" />

The number of respondents with Bachelor's and Master's degree is definitely going up over time.


#### Respondent Job Titles

There are some differences in the way data about job titles was collected across the years. For example, 

- The title **Machine Learning Engineer** was introduced in 2020.
- Year 2018 had quite a lot of titles that were dropped in 2019 and 2020.

We retain only the list of common titles, with the exception of **Machine Learning Engineer**. The titles that we drop from 2018 had very few respondents. On the other hand, those reporting a title of **Machine Learning Engineer** is not an insignificant number. Besides, this is something we will see in future surveys, so it makes sense to retain it.


<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-9-1.png" width="1344" />

We have organized the plot so that the titles on the left side of the plot are those which contain the majority of the respondents that program in **R only**.

We notice that the most common titles reported by **R only** Programmers are Data Scientist, Data Analyst and Business Analyst: we also see dip in the number of respondents for these titles. In fact, we see a dip in the numbers for these titles for those that program in both **Python and R**. In contrast, we notice a small uptick in the numbers of Statisticians, but this rise in Statistician numbers is not commensurate with the dip in Business Analysts and Data Analysts

As for those programming in **Python only**, we see that the numbers of Business Analysts and Data Analysts going up. The number of Data Scientists programming in **Python only** is also going up.

Perhaps there is an association between the Educational Background and Job Titles. Let's see if the educational background of Business Analysts and Data Analysts programming in R is primarily Bachelor's Degree and Master's Degree.

From the two plots below, it is clear that majority of the Data Analysts and Business Analysts who program in R have a Bachelor's or Master's degree in 2018. This is true of Python also.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-10-1.png" width="1344" />


Over the years,the number of respondents with Bachelor's and Master's degree is increasing overall, but these numbers are falling when we consider only those respondents that are programming in R.

> Either, Business Analysts and Data Analysts programming in R are not participating in numbers compared to previous years leading to the dip.

> Or perhaps, there are fewer active Business Analysts and Data Analysts programming in R. If so, is there an underlying reason? Let's check on compensation numbers for R Programmers vis-a-vis Python programmers to see if there is not enough incentive to program in R.


#### Comparing Compensation for R and Python Programmers

The following chart shows the percentage of respondents in different compensation levels and respondents using R are represented well in all compensation levels. There are very few respondents at the very high compensation levels and there is R representation in those as well.

So it cannot be concluded that lower compensation is a deterring factor in R adoption.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-11-1.png" width="1152" />

The dip in number of respondents that program in R, over the years, can be directly attributed to fewer respondents in the Business Analyst and Data Analyst jobs.

As opposed to R, Python programmers have a larger range of job titles. This perhaps explains to some extent the overall lower numbers for R. However, the number of Python respondents are larger that those of R, even in these job titles that have R representation.

If the lower number of R respondents as representative of the overall numbers of R programmers in India, it is not clear why that would be.

There is a large number of tools in the R eco-system for these tasks, not to mention that it is generally easy to start with R. The packages in the **`tidyverse`** universe make it relative easy to perform data analysis and create powerful visualizations. *All the plots in this blog post were created using R*. Besides, the **`Shiny`** package makes it easy to share analysis on the web. R also has a large number of packages for Machine Learning. In addition, there is a strong community support. 

> Additional surveys regarding attitude towards R may help shed more light on this.

We will now deep dive into the use of R, to better understand how R is being used in India.

## Part III: R Usage in India

In our analysis, while our focus is on respondents that program in R only, we include those respondents who program in both R and Python to see if there are any similarities.

### Activities Performed by R Programmers
We begin by looking at typical activities performed by respondents who use R.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-12-1.png" width="1152" />

Respondents that program in R only clearly perform a range of activities. The primary activity of all Job Titles is to **Analyze and understand data**.

What is interesting about the above plot is that the Data Analyst, the Data Scientist, the Research Scientist and the Statistician are all performing almost the same activities. And to some extent, this is true for the Business Analyst: the primary exception being that Business Analysts do not build prototypes.

Let's look at the number of activities performed by R programmers, on average.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-13-1.png" width="1344" />

There is a wide variation. In general, those in smaller teams perform fewer different types of tasks. Statisticians and Data Scientists seem to be performing a large variety of tasks, on average. Besides, the profile mix varies by team size.

### Visualization Tools
Effective visualizations are important for data science teams.

The following plot shows the Visualization tools employed by respondents who use R: we are primarily interested in seeing the use of **`ggplot`** and **`Shiny`**.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-14-1.png" width="1344" />

The findings are as expected. Those that program in R and Python use more of **`Matplotlib`** and **`Seaborn`**. What is interesting is that a comparable number of those who program in both R and Python, also use **`ggplot`**.

On the other hand, almost half of those who program in R only use **`ggplot`**. While the number is impressive, one would expect a higher number.

And when it comes to **`Shiny`**, only 13% of those who program in R only use it. Given the otherwise massive popularity of Shiny, this is very low. Tools similar to Shiny are just about coming up in the Python ecosystem, so the low number cannot be attributed to preference for Python based tools.

The percentages for 2018 and 2019 for **`ggplot`** and **`Shiny`** are not much different. These are not presented here for brevity, since they do not really contribute much to the discussion.

Let's see if there is a differences in use of **`ggplot`** and **`Shiny`** across titles for **R Programmers**.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-15-1.png" width="1152" />

Considering those that program in R only (the graph at the left), the small numbers for ggplot do come as a surprise. The numbers for Shiny are also small and that could be because not everyone will want to share their results on the Web.

However, if we look at those that program in both R and Python, we notice that Shiny is more popular with Data  Scientist. This is true of ggplot as well, which is used by Data Analysts and Business Analysts.

Overall, those that program in both R and Python seem to be leveraging the R eco-system better than those that program in R only.

### Machine Learning Libraries and Algorithms

The plot below shows the different Machine Learning libraries used by R Programmers.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-16-1.png" width="1344" />

Clearly, R Programmers employ a large number of popular Machine Learning libraries. It is no surprise to see **Caret** package scoring the highest for R only respondents. It will be interesting to watch for **tidymodels** next year.

Notice that 21% of R only respondents, do not use any Machine Learning libraries.

The plot below shows the Machine Learning methods employed by R Programmers.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-17-1.png" width="1344" />

Linear Regression seems to be the most popular machine learning algorithm used. Indeed, as per the executive summary referred to at the beginning of this post, Linear Regression is the most popular method among Data Scientists, so this does not come as a surprise.

### Size of Company and Size of Data Science Teams

We close this section with an exploration of the size of companies of respondents who use R. We also investigate typical team sizes.

We consider respondents that program in R only.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-18-1.png" width="1152" />

We see that R programmers are represented in companies of all sizes.

As far as team sizes go, R programmers work in small and large team sizes.

Of interest is to note that 8 people work in team size of 0. This is most likely a lone individual.

## Closing Notes

Clearly, the prevalence of R in India lags Python by a large number.

In my own work, I move between R and Python seamlessly. In other words, both have their place in the sun and the choice should depend on the task at hand.

A strong eco-system of both languages enriches the Data Science community, enabling them to do more and better.

The R eco-system has a large set of tools for data scientists and machine learning practitioners. Perhaps these need to be introduced to the community in India.

With that in mind, I have launched beginner level courses in R on [Coursera](https://www.coursera.org). These courses illustrate that it is easy to get started with R and with a few hours of effort, one can create and deploy a fun Web App using R. You can find a list of these courses on the [My Courses](/courses) tab.

