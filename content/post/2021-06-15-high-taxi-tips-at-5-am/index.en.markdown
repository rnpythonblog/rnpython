---
title: High Taxi Tips at 5 am
author: Manohar Mulchandani
date: '2021-06-15'
slug: high-taxi-tips-at-5-am
categories:
  - R
tags:
  - Analytics
subtitle: "Why do New Yorkers Pay high tips at 5 am in the morning"
summary: "Why do New Yorkers Pay high tips at 5 am in the morning"
authors: []
lastmod: '2021-06-15T10:34:50+05:30'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

<style>
body {
  background-color:cornsilk;
}
</style>

The NYC Taxi Trips dataset is a quite popular, as evinced from a large number of blog posts. The dataset is available in the form of CSV files, organized by month and also by year. The CSV files contain anonymized information about the trip such as pickup and drop off time, pickup and drop off location, trip duration, fare amount and tip amount. It is often used to build models to predict tip amount for a taxi trip.

“How much should one tip?” when in New York. Let’s see if this dataset is any guide for that.

Shown below is a bar graph that plots average tip amounts for taxi
trips in 2019 by the hour. The raw data is available from this [NYC Open Data
page](2019%20Data:%20https://data.cityofnewyork.us/Transportation/2019-Yellow-Taxi-Trip-Data/2upf-qytp).

There were \~84 million trips undertaken in 2019 and thus, on average, about 3.5 million trips at each hour. Thus, each bar represents an average of \~3.5 million trips. The large number of trips will iron out any outliers.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/chnk1-1.png" width="75%" height="300px" style="float:right; padding:10px" />

<br>

> Notice that the average tip amount for trips taken between 5 am and 6 am is the highest at \$2.4.

<br>

That is odd. Most people are in bed or are getting up at around 5 am. If you ask me if people would be sleepy at 5 am, I would say, yes. If you asked me if people are generous at 5 am, I wouldn’t know offhand. “Please look at data,” is the best I might be able to muster.

Since I had some data, I decided to investigate further.

### Data Drill down

**What is causing people to tip higher at 5 am?**

-   Is this a different type of taxi rider ?
-   Are these different types of trips ?
-   Is the data just wrong ?

Since we do not have data about the passengers, we cannot investigate Option
1.

Before we jump to conclusion about data quality, let’s drill down a bit
further. Each bar in the graphic above averages 3.5 million rides, which is a lot of rides. The large size of data enables us to drill down further and explore patterns.

Let’s split this data month wise and then let’s see the average tip
amounts at all hours, for each month.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-4-1.png" width="960" />

> We can easily make out that the average tip amount is consistently high for trips between 5 am and 6 am, across all months. Something is clearly happening here.

If we look closely, in January and March, the highest average tip is during the late hours of the day. But it is a tad difficult to make this out.

Here is an alternate visualization: it shows the tip amounts and the cells are shaded according to the tip amount: higher tips have a darker shade.

<div id="urjjntnkcz" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#urjjntnkcz .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: none;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#urjjntnkcz .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#urjjntnkcz .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#urjjntnkcz .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#urjjntnkcz .gt_bottom_border {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#urjjntnkcz .gt_col_headings {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#urjjntnkcz .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#urjjntnkcz .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#urjjntnkcz .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#urjjntnkcz .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#urjjntnkcz .gt_column_spanner {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#urjjntnkcz .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#urjjntnkcz .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#urjjntnkcz .gt_from_md > :first-child {
  margin-top: 0;
}

#urjjntnkcz .gt_from_md > :last-child {
  margin-bottom: 0;
}

#urjjntnkcz .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: none;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#urjjntnkcz .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#urjjntnkcz .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#urjjntnkcz .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#urjjntnkcz .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#urjjntnkcz .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#urjjntnkcz .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#urjjntnkcz .gt_table_body {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#urjjntnkcz .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#urjjntnkcz .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#urjjntnkcz .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#urjjntnkcz .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#urjjntnkcz .gt_left {
  text-align: left;
}

#urjjntnkcz .gt_center {
  text-align: center;
}

#urjjntnkcz .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#urjjntnkcz .gt_font_normal {
  font-weight: normal;
}

#urjjntnkcz .gt_font_bold {
  font-weight: bold;
}

#urjjntnkcz .gt_font_italic {
  font-style: italic;
}

#urjjntnkcz .gt_super {
  font-size: 65%;
}

#urjjntnkcz .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 65%;
}
</style>
<table class="gt_table">
  <thead class="gt_header">
    <tr>
      <th colspan="13" class="gt_heading gt_title gt_font_normal" style><h3 align = 'left'>High Tip Amount Hours</h2></th>
    </tr>
    <tr>
      <th colspan="13" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style><h4 align = 'left' font-color = 'red'>Here we show data only for those hours in the dataset which have the highest tip value in one of the 12 months</h4></th>
    </tr>
  </thead>
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1"></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Jan</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Feb</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Mar</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Apr</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">May</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Jun</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Jul</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Aug</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Sep</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Oct</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Nov</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Dec</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 5</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFBD05; color: #000000;">1.98</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCB2B; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.48</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.52</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.49</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF9600; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.48</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.55</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.62</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.61</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 0</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCD35; color: #000000;">1.95</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFE187; color: #000000;">2.24</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFC824; color: #000000;">2.33</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFC823; color: #000000;">2.36</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFC20E; color: #000000;">2.38</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.37</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF9D00; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFE8A2; color: #000000;">2.31</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCE37; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFE491; color: #000000;">2.32</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFD54F; color: #000000;">2.39</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 19</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">1.88</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.20</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.50</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.20</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.22</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.25</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.18</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.14</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.25</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.28</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 22</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.05</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF9600; color: #000000;">2.36</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCB2B; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFB601; color: #000000;">2.38</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFBB04; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFB802; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF9E00; color: #000000;">2.33</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFB602; color: #000000;">2.30</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFA500; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFBC04; color: #000000;">2.44</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCE38; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFCF3C; color: #000000;">2.41</td></tr>
  </tbody>
  
  
</table>
</div>

<br>

> The average tip for trips between 5 am and 6 am is highest for 9 out of 12 months. The highest tip for other three months occurs during the late hours of the day.

Let check if this pattern also holds out across days.

<div id="cmcodawlpa" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#cmcodawlpa .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: none;
  background-color: #FFFFFF;
  width: auto;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #A8A8A8;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #A8A8A8;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
}

#cmcodawlpa .gt_heading {
  background-color: #FFFFFF;
  text-align: center;
  border-bottom-color: #FFFFFF;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cmcodawlpa .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: #FFFFFF;
  border-bottom-width: 0;
}

#cmcodawlpa .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: #FFFFFF;
  border-top-width: 0;
}

#cmcodawlpa .gt_bottom_border {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cmcodawlpa .gt_col_headings {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#cmcodawlpa .gt_col_heading {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  padding-left: 5px;
  padding-right: 5px;
  overflow-x: hidden;
}

#cmcodawlpa .gt_column_spanner_outer {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#cmcodawlpa .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#cmcodawlpa .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#cmcodawlpa .gt_column_spanner {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: bottom;
  padding-top: 5px;
  padding-bottom: 6px;
  overflow-x: hidden;
  display: inline-block;
  width: 100%;
}

#cmcodawlpa .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
}

#cmcodawlpa .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  vertical-align: middle;
}

#cmcodawlpa .gt_from_md > :first-child {
  margin-top: 0;
}

#cmcodawlpa .gt_from_md > :last-child {
  margin-bottom: 0;
}

#cmcodawlpa .gt_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  margin: 10px;
  border-top-style: none;
  border-top-width: 1px;
  border-top-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
  vertical-align: middle;
  overflow-x: hidden;
}

#cmcodawlpa .gt_stub {
  color: #333333;
  background-color: #FFFFFF;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#cmcodawlpa .gt_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cmcodawlpa .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#cmcodawlpa .gt_grand_summary_row {
  color: #333333;
  background-color: #FFFFFF;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#cmcodawlpa .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#cmcodawlpa .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#cmcodawlpa .gt_table_body {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#cmcodawlpa .gt_footnotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cmcodawlpa .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#cmcodawlpa .gt_sourcenotes {
  color: #333333;
  background-color: #FFFFFF;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
  border-left-style: none;
  border-left-width: 2px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
}

#cmcodawlpa .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#cmcodawlpa .gt_left {
  text-align: left;
}

#cmcodawlpa .gt_center {
  text-align: center;
}

#cmcodawlpa .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#cmcodawlpa .gt_font_normal {
  font-weight: normal;
}

#cmcodawlpa .gt_font_bold {
  font-weight: bold;
}

#cmcodawlpa .gt_font_italic {
  font-style: italic;
}

#cmcodawlpa .gt_super {
  font-size: 65%;
}

#cmcodawlpa .gt_footnote_marks {
  font-style: italic;
  font-weight: normal;
  font-size: 65%;
}
</style>
<table class="gt_table">
  <thead class="gt_header">
    <tr>
      <th colspan="8" class="gt_heading gt_title gt_font_normal" style><h3 align = 'left'>High Tip Amount Hours</h2></th>
    </tr>
    <tr>
      <th colspan="8" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style><h4 align = 'left' font-color = 'red'>Here we show data only for those hours in the dataset which have the highest tip value in one of the 7 days</h4></th>
    </tr>
  </thead>
  <thead class="gt_col_headings">
    <tr>
      <th class="gt_col_heading gt_columns_bottom_border gt_left" rowspan="1" colspan="1"></th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Sun</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Mon</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Tue</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Wed</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Thu</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Fri</th>
      <th class="gt_col_heading gt_columns_bottom_border gt_right" rowspan="1" colspan="1">Sat</th>
    </tr>
  </thead>
  <tbody class="gt_table_body">
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 0</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.09</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.53</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.37</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFB401; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFC416; color: #000000;">2.24</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 5</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFA400; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF8C00; color: #000000;">2.52</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.27</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFC107; color: #000000;">2.42</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFA500; color: #000000;">2.47</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.55</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.38</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 22</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFA000; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF9800; color: #000000;">2.42</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.46</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.49</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.26</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF8E1; color: #000000;">2.09</td></tr>
    <tr><td class="gt_row gt_left gt_stub" style="background-color: #FFF8DC; font-weight: bold; border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent;">Hour 23</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FF6F00; color: #000000;">2.50</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFE28C; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFAA00; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFB300; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFA500; color: #000000;">2.47</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFF1C4; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="border-left-width: 1px; border-left-style: solid; border-left-color: transparent; border-right-width: 1px; border-right-style: solid; border-right-color: transparent; border-top-width: 1px; border-top-style: solid; border-top-color: transparent; border-bottom-width: 1px; border-bottom-style: solid; border-bottom-color: transparent; background-color: #FFE9A7; color: #000000;">2.13</td></tr>
  </tbody>
  
  
</table>
</div>

> The average tip amount for trips between 5 am and 6 on Fridays and Saturday. For some other days, it is close to the highest amount. The other three hours are night time hours, and all between 10 am to 1 pm.</font>

> 5 am does seem to stand out.

Let’s see if the type of trip undertaken at 5 am is different.

## Investigate Type of Trips

Perhaps the trips between 5 am and 6 am are longer trips; or perhaps these are
trips to a different type of location. Airport trips are typically
longer and they are a different type of destination. Let’s see if there
are more airport trips between 5 am and 6 am.</font>

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-8-1.png" width="960" />

> We have a surprising finding: the tip amounts are actually the lowest at 5 am for non-airport trips.

Tip amounts are generally high for airport trips. In fact, the highest
average tip amount is at 4 pm in the afternoon. And even the non-airport
average tip amount is higher at 4 pm as compared to 5 am in the morning.
Yet the overall average at 5 am is high.

Perhaps there are more airport trips as compared to non-airport trips at 5 am that is pushing up the average. Let’s check that.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-9-1.png" width="960" />

The number of trips to airport at 5 am is much less than the number of non-airport trips.

> Only 20% of the trips between 5 am and 6 am are to the airport. If we look at trips between 4pm and 5pm, only 10% of the trips are airport trips. And that may be the clue.

Let’s look at the relative percentages of Airport and Non Airport Trips

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-10-1.png" width="960" />

The relative percentage of airport trips between 5 am and 6 am is higher
and since that is higher than any other hour, the overall contribution
on high tips is higher for trips between 5 am and 6 am. This results in
an overall higher average tip for trips between 5 am and 6 am.

Please note that trips to the airport always result in high tips,
regardless of the hour.

### Closing Notes

As we can see, New Yorkers are really not paying high tips at 5 am in the morning. The real finding here is that there is a higher percentage of trips to the airport at 5 am in the morning. The higher average tip thus may be an artifact of flight schedules.

It helps to look beyond a simple average. This is especially true when we are looking at large datasets.

This blog post was created as a RMarkdown document, using [RStudio IDE](https://www.rstudio.com/products/rstudio/). The code can be found [here](https://github.com/rnpythonblog/rnpython/blob/main/content/post/2021-06-15-high-taxi-tips-at-5-am/index.en.Rmarkdown). All the plots were created using the ggplot2 R Package.
