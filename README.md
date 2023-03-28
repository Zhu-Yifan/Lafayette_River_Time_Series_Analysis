# Introduction
This repository is my capstone project in course OEAS895 —"Linking wind, tide, and current velocity with bottom nutrient concentrations in the Lafayette River" 

## Table of content
|Data Cleaning|Exploratory Data Anlysis |Exploratory Data Anlysis |
|:-----------------:|:-------------------------------------:|:------------------------:|
|[Data cleaning and quality control](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Data_cleaning_quality_control.ipynb)|[Time-series analysis of YSI data](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Time_Series_Analysis.ipynb)|[Wind data analysis](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Wind_Analysis.ipynb)|
|...|...|...|


# Research Background
In shallow estuary system, wind plays an important role in nutrient variability, primarily through wind/storm driven sediment resuspension events. Additionally, wind can also impact tides by either amplifying or reducing their height, depending on the strength and direction of the wind. This, in turn, might further increase or decrease the residence time and complicate the nutrient dynamics. The Lafayette River is a shallow, eutrophic, and microtidal tributary of the lower Chesapeake Bay (see the map below), recent research from my lab has observed several strong nutrient (especially, ammonium) pulses throughout the summertime monitoring program in multiple years. One intuitive speculation is that strong wind may cause sediment re-suspension, injecting high concentration of nutrient into the overlaying water column. Another plausible explanation is that those abundant nutrients may be directly from the groundwater discharge. As strong wind events dissipate, tide height may decrease, alleviating hydrostatic pressure and thus inducing more groundwater discharge to the Lafayette River. However, a mechanistic understanding of the primary cause of nutrient pulses in the Lafayette River remains unclear. 

<p align="center">
  <img src="https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/figures/Lafayette%20River_map.png" alt="Figure 1. Study area, showing two sampling sites, one at the Norfolk Yacht and Country Club (NYCC), near the mouth of the Lafayette River, and another at Ashland Circle (AC), near the headwaters of the Lafayette River. ">
</p>



# Obejective

Using a supervised machine learning model to find which process is the primary casue of the nutrient pulses observed in the Lafayette River during summer 2018-2020.
# Data science approach
  (1) The data wrangling pipeline
  
  
 * Data collection: gathering raw data from various sources including ADCP mooring, YSI mooring, discrete nutrient samples, and meteorological data (wind,     precipitation).  
  
 * Data cleaning: fill data gaps, filter out the outliers. This step will go back and forth between statistics and visualization through exploratory data analysis.  
  
 * 	Data validation: verify the accuracy and integrity of the data.   
  
 * 	Data storage: store the cleaned data in certain format or folder that can be used for futher analysis.
 
 (2) Time-Series Analysis
 * Use Python packages such as statsmodels, Prophet, and ARIMA to perform time-series analysis on the monitoring data.
 * This may involve fitting time-series models and detecting anomalies.
 
 
 (3) Supervised Machine Learning (Regression):
 
 * Cross-correlation wind speed with significant tide height and current velocities 
 
 * Going through feature-selection for model input
 
 * Use selected features (variables) such as tide height and wind speed/direction as proxy to predict nutrient concentrations 
 
 * validate the model


### List of data/variables
|Frequency|Variables|Variables|
|:-----------------:|:-------------------------------------:|:------------------------:|
|High frequency|Current velocity from ADCP (~6 mins)|Tide height and chlorophyll from YSI mooring (~15 min)|
|Intermediate frequency  |Wind speed and wind direction (hourly) |Precipitation (daily)|
|Low frequency |Discrete nutrient concentrations (NH4+, NO3-) <br> (48-72 hours)|

### Description of the datasets 
  The datasets used in the model were all time-series data collected by different sources and contain different frequencies as listed in the table above.
  
  * YSI mooring data were obtained as a part of harmful algal bloom monitoring program from Mulholland’s lab in summer 2018-2020. 
  * Current velocity data were collected  as a part of Dr. Zimmerman’s field study class with undergraduates. These two datasets were both collected at Norfolk Yacht and Country Club (NYCC) in summer 2020 and have high sampling frequency. 
  * The meteorological dataset includes wind speed/direction and daily precipitation were collected at Norfolk Naval Station in summer 2020 and downloaded from NOAA national climate data center (https://www.ncdc.noaa.gov/cdo-web/datatools/lcd). This dataset has intermediate sampling frequencies. 
  * The discrete nutrient data were collected at bottom depth at Norfolk Yacht and Country Club in summer 2018-2020. The sampling frequency was three times a week (Mon/Wed/Fri). 

