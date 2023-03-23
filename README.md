# Introduction

In shallow estuary system, wind plays an important role in nutrient variability, primarily through wind/storm driven sediment resuspension events. Additionally, wind can also impact tides by either amplifying or reducing their height, depending on the strength and direction of the wind. This, in turn, might further increase or decrease the residence time and complicate the nutrient dynamics. The Lafayette River is a shallow, eutrophic, and microtidal tributary of the lower Chesapeake Bay, recent research from my lab has observed several strong nutrient (especially, ammonium) pulses throughout the summertime monitoring program in multiple years. One intuitive speculation is that strong wind may cause sediment re-suspension, injecting high concentration of nutrient into the overlaying water column. Another plausible explanation is that those abundant nutrients may be directly from the groundwater discharge. As strong wind events dissipate, tide height may decrease, alleviating hydrostatic pressure and thus inducing more groundwater discharge to the Lafayette River. However, a mechanistic understanding of the primary cause of nutrient pulses in the Lafayette River remains unclear. 
# Obejective

Using a supervised machine learning model to find which process is the primary casue of the nutrient pulses observed in the Lafayette River during summer 2018-2020.
# Data science approach
  The data wrangling pipeline includes the following steps:
  
  
 * Data collection: gathering raw data from various sources including ADCP mooring, YSI mooring, discrete nutrient samples, and meteorological data (wind,     precipitation).  
  
 * Data cleaning: fill data gaps, filter out the outliers. This step will go back and forth between statistics and visualization through exploratory data analysis.  
  
 * 	Data validation: verify the accuracy and integrity of the data.   
  
 * 	Data storage: store the cleaned data in certain format or folder that can be used for futher analysis.
 
 The workflow of supervised machine learning model:
 
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
  * Current velocity data were collected  as a part of Dr. Zimmerman’s field study class with undergraduates. These two datasets were both collected at Norfolk Yacht and Country Club in summer 2020 and have high sampling frequency. 
  * The meteorological dataset includes wind speed/direction and daily precipitation were collected at Norfolk Naval Station in summer 2020 and downloaded from NOAA national climate data center (https://www.ncdc.noaa.gov/cdo-web/datatools/lcd). This dataset has intermediate sampling frequencies. 
  * The discrete nutrient data were collected at bottom depth at Norfolk Yacht and Country Club in summer 2018-2020. The sampling frequency was three times a week (Mon/Wed/Fri). 

