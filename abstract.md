# Leveraging Environmental Sensor Data for Predictive Modeling and Causal Analysis of Grapevine Diseases

Grapevines are a cornerstone of the global fruit and wine industries but face persistent threats from diseases such as powdery mildew, downy mildew, and bacterial leaf spot. These diseases compromise yield and fruit quality. Moreover, grapevine diseases are often less studied in the forecasting of plant diseases. This project aims to use the ["Grape Disease Dataset,"](https://pmc.ncbi.nlm.nih.gov/articles/PMC11190471/#sec0004) comprising 10,000 records of environmental parameters—temperature, humidity, and leaf wetness—collected via sensors across grape-growing regions, alongside disease incidence data for key pathogens. Our goal is to develop a predictive framework for forecasting grapevine disease outbreaks.

We're interested in applying causal analysis and ML techniques to uncover drivers for grapevine diseases. The dataset above provides only a few variables, however (temperature, humidity, and leaf wetness). We're curious to explore if these variables can sufficiently predict, or monitor, outbreaks. In terms of feedback, we're unsure of whether to look for additional environment variables to inform this disease prediction, and/or how we can approach going about finding this type of data. 

In terms of causal analysis, we're interested in identifying directional relationships between environmental factors (e.g., prolonged leaf wetness) and disease onset, accounting for other confounding variables like seasonal weather patterns. We plan to use time-series based and classification ML models to capture spatial-temporal patterns and non-linear interactions in the data.

For our feature engineering, we're interested in deriving new predictors (and interested in any feedback or ideas here, as well), such as cumulative humidity hours, temperature-humidity interaction, leaf wetness duration, which we aim to analyze in context of the environmental requirements for various pathogens to develop. 

By combining causal inference with ML forecasting, this project aims to deliver new insights that can be used to better model and predict grapevine health. 

