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
In this assignment, you will work with actual, measured climate data to better understand trends in regional and global climate, while simultaneously improving your analytical and graphic composition skills. Specifically, it is desired that this assignment will:
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
- Data is recorded in hundredths of a degree (i.e. you need to divide values by 100 to get to degrees celcius). **Missing monthly values are represented as -9999 in the data**. As such, you must decide how to handle bad/missing data to ensure that presented data is accurate, representative, and not misleading. 

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

## 6. Assessment Rubric
<img src="a2-rubric.png" alt="Assessment rubric" width="700" style="border: 1px solid darkgrey">
