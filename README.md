# Introduction
This repository is my capstone project in the data science course OEAS895 —"Linking wind, tide, and current velocity with bottom nutrient concentrations in the Lafayette River" 

## Table of content
|Data Cleaning|                                                                             Exploratory Data Anlysis                                                                              |                                                                       Exploratory Data Anlysis                                                                       |                                                                               Model                                                                                |
|:-----------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|[Data cleaning and quality control](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Data_cleaning_quality_control.ipynb)|              [Time-series analysis of YSI data](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Time_Series_Analysis.ipynb)               |  [Wind-Tide-WaterFlux-Nutrient EDA01](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Wind_Tide_Nutrient_Part01_EDA.ipynb)   |  Classification model <br> (Ongoing) |
|...|                         [Wind data analysis](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Wind_Analysis.ipynb)                         | [Wind-Tide-WaterFlux-Nutrient EDA02](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Wind_Tide_Nutrient_Part01_EDA_02.ipynb) |                                                                                ...                                                                                 |
|...|[Chesapeake Bay water quality monitoring ](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/notebooks/Chesapeake_Bay_Program_Water_Quality_EDA.ipynb) |  ... |                                                                                ...                                                                                 |


# Research Background
In shallow estuary system, wind plays an important role in nutrient variability, primarily through wind/storm driven sediment resuspension events. Additionally, wind can also impact tides by either amplifying or reducing their height, depending on the strength and direction of the wind. This, in turn, might further increase or decrease the residence time and complicate the nutrient dynamics. The Lafayette River is a shallow, eutrophic, and micro-tidal tributary of the lower Chesapeake Bay (see the map below), recent research from my lab has observed several strong nutrient (especially, ammonium) pulses throughout the summertime monitoring program in multiple years. One intuitive speculation is that strong wind may cause sediment re-suspension, injecting high concentration of nutrient into the overlaying water column. Another plausible explanation is that those abundant nutrients may be directly from the groundwater discharge. As strong wind events dissipate, tide height may decrease, alleviating hydrostatic pressure and thus inducing more groundwater discharge to the Lafayette River. However, a mechanistic understanding of the primary cause of nutrient pulses in the Lafayette River remains unclear. 

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
 
 
 (3) Supervised Machine Learning (Classification):
 
 * Make a table with nutrient as target variables. List columns including associated wind speed, direction, tide hight, accumulcated tide height, max/min tide height, water volume fluxes, can go back one day, two/three days,  
 
 * Build a classification model  
 
 * validate the model


### List of data/variables
|Frequency|                                                                                      Variables                                                                                      |Variables|
|:-----------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------:|
|High frequency|[Water flux <br> (~15 mins)](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/data/processed/Waterflux_2020.csv)                    |[Tide, temperature, salinity, and chlorophyll from YSI mooring (~15 min)](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/tree/master/data/interim/Mooring_2020)|
|Intermediate frequency  |             [Wind speed and wind direction (hourly)](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/data/external/Wind_hourly_2020.csv)              |[Precipitation (daily)](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/data/external/Precipitation_daily_2020.csv)|
|Low frequency | [Discrete nutrient concentrations (NH4, NO3) <br> (48-72 hours)](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/data/processed/Nutrient_2020_V4.CSV) |

### Description of the datasets 
  The datasets used in the model were all time-series data collected by different sources and contain different frequencies as listed in the table above.
  
  * YSI mooring data were obtained as a part of harmful algal bloom monitoring program from Mulholland’s lab in summer 2018-2020. 
  * Current velocity data were collected  as a part of Dr. Zimmerman’s field study class with undergraduates. These two datasets were both collected at Norfolk Yacht and Country Club (NYCC) in summer 2020 and have high sampling frequency. 
  * The meteorological dataset includes wind speed/direction and daily precipitation were collected at Norfolk Naval Station in summer 2020 and downloaded from NOAA national climate data center (https://www.ncdc.noaa.gov/cdo-web/datatools/lcd). This dataset has intermediate sampling frequencies. 
  * The discrete nutrient data were collected at bottom depth at Norfolk Yacht and Country Club in summer 2018-2020. The sampling frequency was three times a week (Mon/Wed/Fri). 

### Python version and packages

* Python version 3.10.9
* All the packages/versions used for this project can be found in [environment.yml](https://github.com/Zhu-Yifan/Lafayette_River_Time_Series_Analysis/blob/master/environment.yml) file.