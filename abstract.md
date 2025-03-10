<!-- # Leveraging Environmental Sensor Data for Predictive Modeling and Causal Analysis of Grapevine Diseases

Grapevines are a cornerstone of the global fruit and wine industries but face persistent threats from diseases such as powdery mildew, downy mildew, and bacterial leaf spot. These diseases compromise yield and fruit quality. Moreover, grapevine diseases are often less studied in the forecasting of plant diseases. This project aims to use the ["Grape Disease Dataset,"](https://pmc.ncbi.nlm.nih.gov/articles/PMC11190471/#sec0004) comprising 10,000 records of environmental parameters—temperature, humidity, and leaf wetness—collected via sensors across grape-growing regions, alongside disease incidence data for key pathogens. Our goal is to develop a predictive framework for forecasting grapevine disease outbreaks.

We're interested in applying causal analysis and ML techniques to uncover drivers for grapevine diseases. The dataset above provides only a few variables, however (temperature, humidity, and leaf wetness). We're curious to explore if these variables can sufficiently predict, or monitor, outbreaks. In terms of feedback, we're unsure of whether to look for additional environment variables to inform this disease prediction, and/or how we can approach going about finding this type of data. 

In terms of causal analysis, we're interested in identifying directional relationships between environmental factors (e.g., prolonged leaf wetness) and disease onset, accounting for other confounding variables like seasonal weather patterns. We plan to use time-series based and classification ML models to capture spatial-temporal patterns and non-linear interactions in the data.

For our feature engineering, we're interested in deriving new predictors (and interested in any feedback or ideas here, as well), such as cumulative humidity hours, temperature-humidity interaction, leaf wetness duration, which we aim to analyze in context of the environmental requirements for various pathogens to develop. 

By combining causal inference with ML forecasting, this project aims to deliver new insights that can be used to better model and predict grapevine health.  -->

## Preliminary Project Overview: Leveraging LANDFIRE and FIRED Data for Wildfire Spread Prediction

Wildfires are a pressing environmental challenge, particularly in regions with complex topography and flammable vegetation, such as parts of the United States. This project proposes to harness topographic and environmental data from **LANDFIRE** alongside detailed wildfire event data—modeled after the **FIRED** curated data (linked below)—to predict wildfire spread rates and enhance simulation capabilities. Focusing on a U.S. region like California, this project aims to develop predictive models that can forecast daily fire spread rates and directions based on topographic and other meteorological features.

**LANDFIRE** ([https://landfire.gov/](https://landfire.gov/)) provides over 20 national geo-spatial layers for the contiguous United States and insular areas (e.g., Alaska, Hawaii, Puerto Rico, Guam, Marshall Islands, American Samoa, Palau), including elevation, slope, aspect, vegetation type, fuel models, and disturbance data. Meanwhile, the **FIRED** datasets offer event-level summaries (e.g., ignition date, total area burned, fire spread rate) and daily progression details (e.g., daily burned area). Since MODIS covers the U.S., we can use FIRED data—such as the existing **FIRED CONUS** datasets ([link](https://github.com/earthlab/firedpy))—to analyze fire event polygons and daily spread data for CONUS from 2001 to 2019. By combining LANDFIRE’s environmental data with FIRED CONUS’s wildfire specifics, we can model and predict fire dynamics effectively.

The project’s methodology will involve preprocessing LANDFIRE and FIRED CONUS data to align spatially and temporally, engineering features like slope gradients or vegetation density, and training machine learning models (e.g., random forests or neural networks) to predict daily fire spread rates (e.g., km²/day), for example, and the overall severity or spatial spread of a wildfire.

## Problem Ideas and Explorations

These are a few directions to explore within this project framework:

1. **Predicting Fire Spread Rate Using Topography**  
   - **Objective**: Develop a model to predict the daily fire spread rate (e.g., km²/day) using topographic features from LANDFIRE, such as elevation, slope, and aspect.  
   - **Exploration**: Investigate whether steeper slopes or specific aspects (e.g., south-facing) correlate with faster fire spread, using FIRED CONUS’s spread rate data as the target variable.

2. **Impact of Vegetation on Wildfire Dynamics**  
   - **Objective**: Analyze how vegetation types (e.g., forests, grasslands) from LANDFIRE influence fire spread rates or total area burned.  
   - **Exploration**: Compare fire behavior across different land cover types in California to identify which are most susceptible to rapid spread.

3. **Simulating Daily Fire Progression**  
   - **Objective**: Create a simulation tool that predicts daily wildfire spread based on initial ignition points and environmental conditions.  
   - **Exploration**: Use FIRED CONUS daily progression data to validate the simulation, testing hypothetical scenarios like altered vegetation or extreme weather conditions.

4. **Historical Trends and Risk Mapping**  
   - **Objective**: Assess trends in fire spread rates over time and map high-risk areas using historical data.  
   - **Exploration**: Explore links between topography, past fire frequency, and climate change impacts, producing risk assessment tools for wildfire-prone regions.

