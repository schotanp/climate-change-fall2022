---
layout: default
title: 02 - Climate Data
nav_order: 4
parent: Assignment Instructions
---

## Contents
- [1. Introduction](#1-introduction)
- [2. Objectives](#2-objectives)
- [3. Submission Details](#3-submission-details)
- [4. Materials and Data](#4-materials-and-data)
- [5. Tasks](#5-tasks)
- [6. Assessment Rubric](#6-assessment-rubric)
- 
# Analyzing and Visualizing Climate Data
iSci 3A12 - Climate Change – Fall 2022  
Individual Assignment #2

|Date Assigned|2022-10-17|
|:--|:--|
|**Date Due**|**2022-11-06**|
|**Weight**|**5 points**|

## 1. Introduction
As is the case with most science disciplines, analyzing and presenting data is a critical task in climate change science. The ultimate purpose of these activities is to construct and convey information as objectively and clearly as possible. To identify and characterize underlying physical processes, a great deal of data are collected as time series--which are unique from other sampled data in that the order of the observations is an important characteristic. Analyses of time series often focus on variables’ time-related correlation (e.g. trends, cycles, etc.), and results are commonly communicated to external audiences--whether scientific or otherwise—using graphic devices such as charts, graphs, and tables. 
Just as it is important to critically assess the methods used to gain an understanding of a phenomenon, it is equally important to scrutinize the way in which results are presented to the reader through graphics. Creating graphs is to some extent a subjective process, and the choices made in displaying information can significantly impact the audience’s resulting understanding and opinions.

## 2. Objectives
In this assignment, you will work with actual, measured climate data to better understand trends in regional and global climate, while simultaneously improving your analytical and graphic composition skills. 
<br>
<br>
- **In the first part** of this assignment, you will use Microsoft Excel (or another analytical tool of your choice) to perform an analysis on a >100 year time series of data from a specific weather station (each student is assigned a different one) as well the global average. You will turn your analyses into a figure that communicates trends in temperature at both scales.  
- **In the second part**, you will have an opportunity to play the role of a climate denier by manipulating presentation of the global temperature time series (but not the actual data) to minimize or refute the observed upward trend. 
- **In the last part**, you will be given freedom to conduct novel analyses using some of the datasets that you have been provided (these are described in the [Materials and Data](#4-materials-and-data) section. 
<br>
In terms of skill and knoweldge development, it is intended that this assignment will:
- provide you with experience and guidance making quality scientific figures.
- increase your appreciation for the importance of figure presentation in conveying a message to an audience.
- familiarize you with climate data and time series analysis.
- further your understanding of the nature of global and regional climate change.
- advance your GitHub and Markdown skills to embed your figures and tables in a web-ready document.

## 3. Submission Details
As with your first assignment, your submission will take the form of a [Markdown](https://www.markdownguide.org/getting-started/) document. Materials for this assignment (as well as a template markdown submission file) are provided to you in the GitHub repository that is created for you in GitHub Classrooms when you click [this link](https://classroom.github.com/a/4gwsqZa3) and clone the repository. To get prepared, you should: 
1. Create your repository for this assignment at this url: [https://classroom.github.com/a/4gwsqZa3](https://classroom.github.com/a/4gwsqZa3).
  - Follow the prompts to open your new repository (it will have a url: ```https://github.com/iSci-3A12/isci3a12-a2-climate-data-<yourgithubname>```)
  - Remember that you can find all your GitHub Classroom repostories at [https://github.com/settings/repositories](https://github.com/settings/repositories). 
2. Read the rest of this instruction document (information about datasets are included in the repository's README.md file, as well. 
3. Open up the ```submission.md``` in your assignment repository--**This is where you will complete your assignment**. While in edit mode, note the additional comments that are added to the document (enclosed by ```<!--``` and ```-->``` characters). These comments provide extra information to you that are not visible in the renderend markdown file.
4. Follow the steps outlined below in the [Tasks](#5-Tasks) section. 
5. Following the due date, Jay will download the repositories to be marked. 

## 4. Materials and Data

A variety of datasets have been downloaded and prepared for use in this assignment. These can all be found in the ```/data``` folder of your cloned assignment repository. Contents of each subdirectory in that folder are described below. 

### 4.1 GISS Surface Temperature Analysis (v4) - Station Data 
- Located in ```/data/station_data/```
- This folder contains comma-separated (csv) text files, each consisting of monthly mean temperature measurements for a weather station somewhere in the world. **This is the primary data you will use for this assignment**. 
  - **Each student has been assigned a different station for the purposes of this assignment**--station assignments are outlined in ```assigned_stations.pdf``` in the repository. 
- This data has been downloaded from the NASA Goddard Institute for Space Studies [GISS Surface Temperature Analysis (v4) Station Data](https://data.giss.nasa.gov/gistemp/station_data_v4_globe/) dataset. These datasets were selected for this assignment because they a) span at least 100 years, b) are of high data quality (i.e. have relatively few missing values), and c) collectively, they cover as much of the globe as possible. Note that large regions of the world are still absent from these selected datasets due to poor quality time series in these areas. 
- Data is recorded in hundredths of a degree (i.e. you need to divide values by 100 to get to degrees celcius). **Missing monthly values are represented as ```-9999``` in the data**. As such, you must decide how to handle bad/missing data to ensure that presented data is accurate, representative, and not misleading. 

### 4.2 Hadley Centre Central England Temperature (CET) Data - Daily and Monthly
- Located in ```/data/CET/```
- These are datasets of daily and monthly temperature measurements (mean, min, max) corresponding to the [Central England Temperature](https://www.metoffice.gov.uk/hadobs/hadcet/) (CET) time series--the longest such continuous record in the world.
- Data Source: http://www.metoffice.gov.uk/hadobs/hadcet/data/download.html

#### 4.2.1 Daily Data
- Files are tab-delimited text, with two columns: Date and one of either mean, max, or min temperatures (in degrees Celsius) 
- ```cet-daily.dat```: Daily average temperature value for all days since 1772. 
- ```cet-max-daily.dat```: Daily maximum temperature value for all days since 1878.
- ```cet-min-daily.dat```: Daily minumum temperature value for all days since 1878.

#### 4.2.1 Monthly Data
- Files are tab-delimited text, with 14 columns. Column 1 is the year; Columns 2 through 13 are monthly temperature values (mean, max, or min); Column 14 is the average annual value of the same temperature measure.
- ```cet-monthly.dat```: Monthly mean temperatures for months since 1659.
- ```cet-max-monthly.dat```: Monthly maximum temperatures for months since 1878.
- ```cet-min-monthly.dat```: Monthly minimum temperatures for months since 1878.

### 4.3 GISS Annual Global Surface Temperature (GISS) 
- Located in in ```/data/global_temperature/```
- Spatially-averaged estimates of global surface temperature.  All data downloaded from: https://data.giss.nasa.gov/gistemp/graphs_v4/
- ```GISS_MeanSfcTemp.txt```: Global Land-Ocean Temperature Index (degrees C; Anomaly with Base: 1951-1980) 
	- **Use this for a global average when comparing to your station**. 
	- Dataset has three columns: Column 1 is the year; Column 2 is the annual average anomaly; Column 3 is the 5-year average anomaly, calculated using a 5-year window centred on the year of interest
	- [Direct link to the data](https://data.giss.nasa.gov/gistemp/graphs_v4/graph_data/Global_Mean_Estimates_based_on_Land_and_Ocean_Data/graph.txt).
	- [Learn more about the Land-Ocean Temperature Index](https://data.giss.nasa.gov/gistemp/faq/#q103).
- ```GISS_MonthlyMeanTemp.txt```: Monthly mean global surface temperature anomalies (degrees C; Base: 1951-1980) provided for a number of different estimate types:
	1. ```Station```: Global anomaly estimated using land and sea air temperature stations only. 
	2. ```Land+Ocean```: The Land-Ocean Temperature Index (see above).
	3. ```Land_Only```: Estimate of Temperature Index for ***land only***.
	4. ```Open Ocean```: Estimate of Temperature Index for ***ocean only***. 
	- [Direct link to the data](https://data.giss.nasa.gov/gistemp/graphs_v4/graph_data/Monthly_Mean_Global_Surface_Temperature/graph.txt)
- ```GISS_Land+Ocean.txt```: Annual Mean Temperature Change over Land and over Ocean (degrees C; Anomaly with Base: 1951-1980)
	- [Direct link to the data](https://data.giss.nasa.gov/gistemp/graphs_v4/graph_data/Temperature_Anomalies_over_Land_and_over_Ocean/graph.txt)
- ```GISS_MeanHemisphereTemp.txt```:  Annual mean Land-Ocean Temperature Index in .01 degrees Celsius by hemispheres and zones (Anomaly with Base: 1951-1980) 
	- [Direct link to the data](https://data.giss.nasa.gov/gistemp/graphs_v4/graph_data/Hemispheric_Temperature_Change/graph.txt)

### 4.4 SDIC Monthly and Annual Sunspot Data (Back to 1749) 
- Located in ```/data/sunspots/```
- Long term record of daily, monthly and annual sunspot numbers.
- Data Source: http://www.sidc.be/silso/datafiles
- ```TotalSunspotsDaily.csv```: Daily sunspot numbers (as a comma-separated file)
	- Column 1: Year 
	- Column 2: Month
	- Column 3: Day 
	- Column 4: Date in fraction of year.
	- Column 5: Daily total sunspot number. A value of -1 indicates that no number is available for that day (missing value).
	- Column 6: Daily standard deviation of the input sunspot numbers from individual stations. A value of -1 indicates that no number is available for that day (missing value).
	- Column 7: Number of observations used to compute the daily value.
	- Column 8: Definitive/provisional indicator. '1' indicates that the value is definitive. '0' indicates that the value is still provisional.
- ```TotalSunspotsAnnual.csv```: Annual avergage sunspot numbers (as a comma-separated file)
	- Column 1: Gregorian calendar year (mid-year date)
	- Column 2: Yearly mean total sunspot number. A value of -1 indicates that no number is available for that day (missing value).
	- Column 3: Yearly mean standard deviation of the input sunspot numbers from individual stations. A value of -1 indicates that no number is available for that day (missing value).
	- Column 4: Number of observations used to compute the yearly mean total sunspot number.
	- Column 5: Definitive/provisional marker. '1' indicates that the value is definitive. '0' indicates that the value is still provisional.
- ```TotalSunspotsMonthly.csv```: Monthly avergage sunspot numbers (as a comma-separated file)
	- Column 1: Year
	- Column 2: Month
	- Column 3: Date in fraction of year.
	- Column 4: Monthly mean total sunspot number. A value of -1 indicates that no number is available for that day (missing value).
	- Column 5: Monthly mean standard deviation of the input sunspot numbers. A value of -1 indicates that no number is available for that day (missing value).
	- Column 6: Number of observations used to compute the monthly mean total sunspot number.
	- Column 7: Definitive/provisional marker. '1' indicates that the value is definitive. '0' indicates that the value is still provisional.

## 5. Tasks
In your submission file, you will create a report with **3 figures, 1 table, and 2 question responses**. These can be inserted into the ```submission.md``` file that has already been created for you in your cloned repository. Your tasks for this assignment are described below: 
### Figure 1
- Plot the annual temperature anomaly time series for your assigned station (in the /station_data/ subdirectory), along with the annual global anomaly temperature anomaly time series. Both series should be plotted as an anomaly from their respective 1951-1980 means (our chosen baseline period). Plot a trend for each time series, using a trend line or a moving average (you have freedom to choose either). 
- Export your figure from Excel as a PNG file and title it ```station-timeseries.png```
- Insert this figure into your ```submission.md``` document. Add a descriptive caption and be sure to indicate the baseline period (1951-1980) in it.
### Table 1
- Create a table displaying the annual and seasonal average temperatures at your site for the past 40 years of measurement, as well as for all previous years in the time series. To create seasonal averages, you should group data from successive three-month periods. e.g.:
	- JFM = average of: Jan, Feb, Mar
	- AMJ =  average of: Apr, May, Jun
	- JAS =  average of: July, Aug, Sep
	- OND =  average of: Oct, Nov, Dec
	- Annual =  average of all months for the year
- For each grouped period, calculate a two-sample t-test to test whether the mean temperature over the past 40 years of available data is significantly different than that from before. Use a significance value of 𝛼 = 0.05.
- Your final table should be structured in the following manner: 
	- 5 Columns: ```| JFM | AMJ | JAS | OND | Annual |```
	- 3 Rows: 
		- Mean T, (in °C) for the last 40 years of available data (most timeseries end in 2021, some end a couple of years earlier)
		- Mean T, (in °C) for the years before the last 40 (there should be no overlap in years) 
		- ΔT, (in °C), or differences in seasonal/annual means from the last 40 years and the previous years (i.e. row 1 – row 2)
		- Significant differences should be bolded and indicated with a trailing plus sign (e.g. 0.331+)
		- The table should have a descriptive title at the top, and a note at the bottom proclaiming: ***"+" denotes significant difference at significance level 𝛼=0.05***

### Question 1: Considering the results shown in Figure 1 and Table 1, summarize how temperatures have (or have not) changed at your assigned station. What are the limitations of your analysis? (150 words or less).

### Figure 2
- Assuming the role of a “climate denier”, create a new figure and modify the presentation of the global temperature anomaly time series to present it in a manner that would support your cause. You are not allowed to falsify the data (i.e. no fabricated or altered data), but you can certainly alter the figure’s presentation to suit your needs.
- Export your figure from Excel as a PNG file and title it ```climate-denier.png```
- Insert this figure into your ```submission.md``` document. Add a descriptive caption and be sure to indicate the baseline period (1951-1980) in it.

### Figure 3
- For this figure, you are asked to perform a more in-depth analysis of your data, and look for relationships within it, or relationships with other variables. You can choose between two general approaches: 
	1. Compare your timeseries (using monthly, seasonal, or annual averages) to any of the other available time series in the Data Pack (or from other sources if you wish), to establish relationships between the two timeseries.  NOTE that you are exploring relationships between two variables (e.g. global temperature anomaly and sunspots), and that plotting two line plots together is a poor form of comparison.
	1. **OR** Use other forms of analyses to examine any of the time series in more depth (e.g. spectral analysis, autocorrelation analysis).  Feel free to be creative.  The only restriction is that you may not construct a simple line plot of the time series (as you’ve already done in Figures 1 and 2).



## 6. Assessment Rubric
<img src="a2-rubric.png" alt="Assessment rubric" width="700" style="border: 1px solid darkgrey">
