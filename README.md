# Introduction

  In shallow estuary system, wind plays an important role in nutrient variability, primarily through wind/storm driven sediment resuspension events. Additionally, wind can also impact tides by either amplifying or reducing their height, depending on the strength and direction of the wind. This, in turn, might further increase or decrease the residence time and complicate the nutrient dynamics. The Lafayette River is a shallow, eutrophic, and microtidal tributary of the lower Chesapeake Bay, recent research from my lab has observed several strong nutrient (especially, ammonium) pulses throughout the summertime monitoring program in multiple years. One intuitive speculation is that strong wind may cause sediment re-suspension, injecting high concentration of nutrient into the overlaying water column. Another plausible explanation is that those abundant nutrients may be directly from the groundwater discharge. As strong wind events dissipate, tide height may decrease, alleviating hydrostatic pressure and thus inducing more groundwater discharge to the Lafayette River. However, a mechanistic understanding of the primary cause of nutrient pulses in the Lafayette River remains unclear. 
# Obejective

  Using a supervised machine learning model that can find which process is the primary casue of the nutrient pulses observed in the Lafayette River during summer.
  
## List of data/variables
|Frequency|Variables|Variables|
|:-----------------:|:-------------------------------------:|:------------------------:|
|High frequency|Current velocity from ADCP (~6 mins)|Tide height and chlorophyll from YSI mooring (~15 min)|
|Intermediate frequency  |Wind speed and wind direction (hourly) |Precipitation (daily)|
|Low frequency |Discrete nutrient concentrations (NH4+, NO3-) (48-72 hours)|
