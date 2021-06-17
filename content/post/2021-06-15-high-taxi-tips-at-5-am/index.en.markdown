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

Sometime back, I was working with NYC Taxi Trip data. The dataset has information about pickup and drop off time, trip duration, fare amount and tip amount. “How much should one tip?” is a frequent question. So I decided to explore tipping behaviour.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/chnk1-1.png" width="75%" height="450px" style="float:right; padding:10px" />

On the right is a chart that shows average tip amounts for NYC taxi
trips in 2019 by the hour. The raw data is available from this [NYC Open Data
page](2019%20Data:%20https://data.cityofnewyork.us/Transportation/2019-Yellow-Taxi-Trip-Data/2upf-qytp).

There were \~84 million trips undertaken in 2019 and thus, on average, about 3.5 million trips per hour. Thus, each bar represents an average of \~3.5 million trips. The largenumber of trips will iron out any outliers.

<br>

> Notice that the average tip amount for trips taken between 5 am and 6 am is the highest at \$2.4.

That was odd. Most people are in bed or are getting up at around 5 am. If you ask me if people would be sleepy at 5 am, I would say, yes. If you asked me if people are generous at 5 am, I wouldn’t know offhand. If if you pushed me further, “Please look at data,” is the best I might be able to muster.

Since I had some data, I decided to investigate further.

### Data Drill down

**What is causing people to tip higher at 5 am?**

-   Is this a different type of taxi rider ?
-   Are these different types of trips ?
-   Is the data just wrong ?

We do not have data about the passengers. So we have to rule out Option
1.

Before we jump to conclusion about data quality, let’s drill down a bit
further. Each bar in the graphic above averages 3.5 million rides, which is a lot of rides. The large size of data enables us to drill down further and explore patterns.

Let’s split this data month wise and then let’s see the average tip
amounts at all hours, for each month.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-4-1.png" width="960" />

> We can easily make out that the average tip amount is consistently high for trips between 5 am and 6 am, across all months. Something is clearly happening here.

While the above plot is useful, it is difficult to see if the tip amount is **ALWAYS** highest for trips between 5 am and 6 am. Here is an alternate visualization: it shows the tip amounts and the cells are shaded according to the tip amount: higher tips have a darker shade.

<div id="pzspjtikzh" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#pzspjtikzh .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: none;
  background-color: cornsilk;
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

#pzspjtikzh .gt_heading {
  background-color: cornsilk;
  text-align: center;
  border-bottom-color: cornsilk;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#pzspjtikzh .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: cornsilk;
  border-bottom-width: 0;
}

#pzspjtikzh .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: cornsilk;
  border-top-width: 0;
}

#pzspjtikzh .gt_bottom_border {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#pzspjtikzh .gt_col_headings {
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

#pzspjtikzh .gt_col_heading {
  color: #333333;
  background-color: cornsilk;
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

#pzspjtikzh .gt_column_spanner_outer {
  color: #333333;
  background-color: cornsilk;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#pzspjtikzh .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#pzspjtikzh .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#pzspjtikzh .gt_column_spanner {
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

#pzspjtikzh .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: cornsilk;
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

#pzspjtikzh .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: cornsilk;
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

#pzspjtikzh .gt_from_md > :first-child {
  margin-top: 0;
}

#pzspjtikzh .gt_from_md > :last-child {
  margin-bottom: 0;
}

#pzspjtikzh .gt_row {
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

#pzspjtikzh .gt_stub {
  color: #333333;
  background-color: cornsilk;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#pzspjtikzh .gt_summary_row {
  color: #333333;
  background-color: cornsilk;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#pzspjtikzh .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#pzspjtikzh .gt_grand_summary_row {
  color: #333333;
  background-color: cornsilk;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#pzspjtikzh .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#pzspjtikzh .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#pzspjtikzh .gt_table_body {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#pzspjtikzh .gt_footnotes {
  color: #333333;
  background-color: cornsilk;
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

#pzspjtikzh .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#pzspjtikzh .gt_sourcenotes {
  color: #333333;
  background-color: cornsilk;
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

#pzspjtikzh .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#pzspjtikzh .gt_left {
  text-align: left;
}

#pzspjtikzh .gt_center {
  text-align: center;
}

#pzspjtikzh .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#pzspjtikzh .gt_font_normal {
  font-weight: normal;
}

#pzspjtikzh .gt_font_bold {
  font-weight: bold;
}

#pzspjtikzh .gt_font_italic {
  font-style: italic;
}

#pzspjtikzh .gt_super {
  font-size: 65%;
}

#pzspjtikzh .gt_footnote_marks {
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
      <th colspan="13" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style><h4 align = 'left' font-color = 'red'>The hours in the dataset which have the highest value in one of the 12 months</h4></th>
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
    <tr><td class="gt_row gt_left gt_stub">Hour 5</td>
<td class="gt_row gt_right" style="background-color: #FFBD05; color: #000000;">1.98</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="background-color: #FFCB2B; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.48</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.52</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.49</td>
<td class="gt_row gt_right" style="background-color: #FF9600; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.48</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.55</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.62</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.61</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 0</td>
<td class="gt_row gt_right" style="background-color: #FFCD35; color: #000000;">1.95</td>
<td class="gt_row gt_right" style="background-color: #FFE187; color: #000000;">2.24</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="background-color: #FFC824; color: #000000;">2.33</td>
<td class="gt_row gt_right" style="background-color: #FFC823; color: #000000;">2.36</td>
<td class="gt_row gt_right" style="background-color: #FFC20E; color: #000000;">2.38</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.37</td>
<td class="gt_row gt_right" style="background-color: #FF9D00; color: #000000;">2.34</td>
<td class="gt_row gt_right" style="background-color: #FFE8A2; color: #000000;">2.31</td>
<td class="gt_row gt_right" style="background-color: #FFCE37; color: #000000;">2.39</td>
<td class="gt_row gt_right" style="background-color: #FFE491; color: #000000;">2.32</td>
<td class="gt_row gt_right" style="background-color: #FFD54F; color: #000000;">2.39</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 19</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">1.88</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.20</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.50</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.20</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.22</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.25</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.18</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.14</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.25</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.28</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 22</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.05</td>
<td class="gt_row gt_right" style="background-color: #FF9600; color: #000000;">2.36</td>
<td class="gt_row gt_right" style="background-color: #FFCB2B; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="background-color: #FFB601; color: #000000;">2.38</td>
<td class="gt_row gt_right" style="background-color: #FFBB04; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="background-color: #FFB802; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="background-color: #FF9E00; color: #000000;">2.33</td>
<td class="gt_row gt_right" style="background-color: #FFB602; color: #000000;">2.30</td>
<td class="gt_row gt_right" style="background-color: #FFA500; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="background-color: #FFBC04; color: #000000;">2.44</td>
<td class="gt_row gt_right" style="background-color: #FFCE38; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="background-color: #FFCF3C; color: #000000;">2.41</td></tr>
  </tbody>
  
  
</table>
</div>

<br>

> The average tip for trips between 5 am and 6 am is highest for 9 out of 12 months.

Let check if this pattern also holds out across days.

<div id="fepfncspnm" style="overflow-x:auto;overflow-y:auto;width:auto;height:auto;">
<style>html {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Helvetica Neue', 'Fira Sans', 'Droid Sans', Arial, sans-serif;
}

#fepfncspnm .gt_table {
  display: table;
  border-collapse: collapse;
  margin-left: auto;
  margin-right: auto;
  color: #333333;
  font-size: 16px;
  font-weight: normal;
  font-style: none;
  background-color: cornsilk;
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

#fepfncspnm .gt_heading {
  background-color: cornsilk;
  text-align: center;
  border-bottom-color: cornsilk;
  border-left-style: none;
  border-left-width: 1px;
  border-left-color: #D3D3D3;
  border-right-style: none;
  border-right-width: 1px;
  border-right-color: #D3D3D3;
}

#fepfncspnm .gt_title {
  color: #333333;
  font-size: 125%;
  font-weight: initial;
  padding-top: 4px;
  padding-bottom: 4px;
  border-bottom-color: cornsilk;
  border-bottom-width: 0;
}

#fepfncspnm .gt_subtitle {
  color: #333333;
  font-size: 85%;
  font-weight: initial;
  padding-top: 0;
  padding-bottom: 4px;
  border-top-color: cornsilk;
  border-top-width: 0;
}

#fepfncspnm .gt_bottom_border {
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#fepfncspnm .gt_col_headings {
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

#fepfncspnm .gt_col_heading {
  color: #333333;
  background-color: cornsilk;
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

#fepfncspnm .gt_column_spanner_outer {
  color: #333333;
  background-color: cornsilk;
  font-size: 100%;
  font-weight: normal;
  text-transform: inherit;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 4px;
  padding-right: 4px;
}

#fepfncspnm .gt_column_spanner_outer:first-child {
  padding-left: 0;
}

#fepfncspnm .gt_column_spanner_outer:last-child {
  padding-right: 0;
}

#fepfncspnm .gt_column_spanner {
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

#fepfncspnm .gt_group_heading {
  padding: 8px;
  color: #333333;
  background-color: cornsilk;
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

#fepfncspnm .gt_empty_group_heading {
  padding: 0.5px;
  color: #333333;
  background-color: cornsilk;
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

#fepfncspnm .gt_from_md > :first-child {
  margin-top: 0;
}

#fepfncspnm .gt_from_md > :last-child {
  margin-bottom: 0;
}

#fepfncspnm .gt_row {
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

#fepfncspnm .gt_stub {
  color: #333333;
  background-color: cornsilk;
  font-size: 100%;
  font-weight: initial;
  text-transform: inherit;
  border-right-style: none;
  border-right-width: 2px;
  border-right-color: #D3D3D3;
  padding-left: 12px;
}

#fepfncspnm .gt_summary_row {
  color: #333333;
  background-color: cornsilk;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#fepfncspnm .gt_first_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
}

#fepfncspnm .gt_grand_summary_row {
  color: #333333;
  background-color: cornsilk;
  text-transform: inherit;
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
}

#fepfncspnm .gt_first_grand_summary_row {
  padding-top: 8px;
  padding-bottom: 8px;
  padding-left: 5px;
  padding-right: 5px;
  border-top-style: none;
  border-top-width: 6px;
  border-top-color: #D3D3D3;
}

#fepfncspnm .gt_striped {
  background-color: rgba(128, 128, 128, 0.05);
}

#fepfncspnm .gt_table_body {
  border-top-style: none;
  border-top-width: 2px;
  border-top-color: #D3D3D3;
  border-bottom-style: none;
  border-bottom-width: 2px;
  border-bottom-color: #D3D3D3;
}

#fepfncspnm .gt_footnotes {
  color: #333333;
  background-color: cornsilk;
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

#fepfncspnm .gt_footnote {
  margin: 0px;
  font-size: 90%;
  padding: 4px;
}

#fepfncspnm .gt_sourcenotes {
  color: #333333;
  background-color: cornsilk;
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

#fepfncspnm .gt_sourcenote {
  font-size: 90%;
  padding: 4px;
}

#fepfncspnm .gt_left {
  text-align: left;
}

#fepfncspnm .gt_center {
  text-align: center;
}

#fepfncspnm .gt_right {
  text-align: right;
  font-variant-numeric: tabular-nums;
}

#fepfncspnm .gt_font_normal {
  font-weight: normal;
}

#fepfncspnm .gt_font_bold {
  font-weight: bold;
}

#fepfncspnm .gt_font_italic {
  font-style: italic;
}

#fepfncspnm .gt_super {
  font-size: 65%;
}

#fepfncspnm .gt_footnote_marks {
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
      <th colspan="8" class="gt_heading gt_subtitle gt_font_normal gt_bottom_border" style><h4 align = 'left' font-color = 'red'>The hours in the dataset which have the highest value in one of the 7 days</h4></th>
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
    <tr><td class="gt_row gt_left gt_stub">Hour 0</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.09</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.53</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.37</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="background-color: #FFB401; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="background-color: #FFC416; color: #000000;">2.24</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 5</td>
<td class="gt_row gt_right" style="background-color: #FFA400; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="background-color: #FF8C00; color: #000000;">2.52</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.27</td>
<td class="gt_row gt_right" style="background-color: #FFC107; color: #000000;">2.42</td>
<td class="gt_row gt_right" style="background-color: #FFA500; color: #000000;">2.47</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.55</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.38</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 22</td>
<td class="gt_row gt_right" style="background-color: #FFA000; color: #000000;">2.41</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="background-color: #FF9800; color: #000000;">2.42</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.46</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.49</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.26</td>
<td class="gt_row gt_right" style="background-color: #FFF8E1; color: #000000;">2.09</td></tr>
    <tr><td class="gt_row gt_left gt_stub">Hour 23</td>
<td class="gt_row gt_right" style="background-color: #FF6F00; color: #000000;">2.50</td>
<td class="gt_row gt_right" style="background-color: #FFE28C; color: #000000;">2.45</td>
<td class="gt_row gt_right" style="background-color: #FFAA00; color: #000000;">2.40</td>
<td class="gt_row gt_right" style="background-color: #FFB300; color: #000000;">2.43</td>
<td class="gt_row gt_right" style="background-color: #FFA500; color: #000000;">2.47</td>
<td class="gt_row gt_right" style="background-color: #FFF1C4; color: #000000;">2.28</td>
<td class="gt_row gt_right" style="background-color: #FFE9A7; color: #000000;">2.13</td></tr>
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

Perhaps there are more airport trips as compared to non-airport trips at 5 am. Let’s check that.

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-9-1.png" width="960" />

> Only 20% of the trips between 5 am and 6 am are to the airport. If we look at trips between 4pm and 5pm, only 10% of the trips are airport trips. And that may be the clue.

Let’s look at the relative percentages of Airport and Non Airport Trips

<img src="{{< blogdown/postref >}}index.en_files/figure-html/unnamed-chunk-10-1.png" width="960" />

The relative percentage of airport trips between 5 am and 6 am is higher
and since that is higher than any other hour, the overall contribution
on high tips is higher for trips between 5 am and 6 am. This results in
an overall higher average tip for trips between 5 am and 6 am.

Please note that trips to the airport always result in high tips,
regardless of the hour.

So, there is no real advantage for the taxi driver to take rides at 5 am
in the morning.

    ## [1] 1.160 1.095 1.020

    ## [1] 1.045 1.095 1.020
