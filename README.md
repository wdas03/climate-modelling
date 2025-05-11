# Wildfire Spread Rate Predictions
Instructions on how to run code. We suggest running in a Jupyter Notebook environment or on Google Colab.
```
git clone https://github.com/wdas03/climate-modelling.git
cd climate-modelling
cd src
pip install -r requirements.txt
```

## Repo Overview
**Important Files:**
- `src/data/conus_eda.ipynb`: EDA on FIRED CONUS and topographic data.
- `src/wildfire_modelling_climate_data.ipynb`: Baseline analyses using ONLY climate variables (no topographic data) for multivariate regression on daily fire spread rate and total area burned, multivariate classification on daily fire spread rate and total area burned severity (Low, Moderate, High), and binary classificaiton of wildfire events from a two week prior window of climate data for specific regions.
- `src/augmented_feature_engineering.ipynb`: Integration of topographic features with climate features from `wildfire_modelling_climate_data.ipynb` and analysis on a deep neural network (DNN).
- `src/data/data_integration_slopes.ipynb`: Data integration of FIRED CONUS dataset with LANDFIRE dataset (getting slopes + elevations of 1km regions around the ignition points in FIRED CONUS)
- `src/data/merge_weather_and_slope.ipynb`: Merge topographic features with climate variables.

## Getting Data
First, download the `FIRED CONUS AK V2` dataset from https://scholar.colorado.edu/concern/datasets/fx719p11c?locale=de. All wildfire data originates from here.

**Note** This is a very large download and will require at LEAST 40GB of disk space to uncompress.

Once your data is ready, we format the important data into csv files for easy handling and running ML.

**Be sure to edit all filepaths according to your environment/setup!** We make our data available to all LionMail users at https://drive.google.com/drive/folders/1drGPNF-rHee4apAsOcTFDDLzJKu5N5IH.

For working with climate-only data (weather variables such as temperature, evapotranspiration, precipiation, etc...), our aggregated, pre-processed dataframe which we run our analyses on is located at https://drive.google.com/file/d/1iG8WW2pRfrVN4SRSfW0Z-mlkFg4fJgYd/view?usp=drive_link (fire_events_with_weather_metrics_augmented.csv) and around 550MB large. To run the notebooks (such as `src/wildfire_modelling_climate_data.ipynb`), this file should be downloaded to a directory called /data in the root directory of this repo. 

### Integrate slope data
Run the `data_integration_slopes.ipynb` notebook and change the file paths accordingly. This will output a csv file with corresponding slope, aspect, and elevation data. For your convenience, the resulting file is `ignition_topography_data.csv`. [Download from Google Drive](https://drive.google.com/file/d/1pr1a_Je8V-NFMvdiVt0EDQ6x99erDUqd/view?usp=drive_link)


### Integrate weather data
Run the `weather.ipynb` notebook and change the API keys and file paths accordingly. To fully recreate, create a subscription with https://open-meteo.com/. With our subscription, we we only had access to data after 01/01/2016, so we prune the original data from ~340k to ~120k rows.

This will allow to make a lot of API calls which is needed as there are over 120000 rows of data to account for. This will output a csv file with corresponding weather data. [Download from Google Drive](https://drive.google.com/file/d/1NFF5LQrX20MmjflPbOWDDDUK1vnGHd-e/view?usp=drive_link)

To combine the slope and weather data, run `src/data/merge_weather_and_slope.ipynb`. This will result in a csv file with over 300 features. [Download from Google Drive](https://drive.google.com/file/d/1NFF5LQrX20MmjflPbOWDDDUK1vnGHd-e/view?usp=drive_link)

### Data Creation, Aggregation, and Feature Engineering
Our main feature engineering is done in `src/wildfire_modelling_climate_data.ipynb`. Running the cells starting from the top, provided the CONUS data is stored in the data directory, will create and query data from external APIs (takes around 7-8 hours on M1 Mac). The main dataframe including our features and labels are stored in `data/fire_events_with_weather_metrics_augmented.csv` and `data/nonfire_events_with_weather_metrics_augmented.csv`. Reading these files in pandas and running our analyses should be straightforward.

## Evaluation
To run EDA, run `src/data/conus_eda.ipynb`.

To run simple out-of-the-box methods, run `src/eval/baseline.ipynb` and change the file paths to data accordingly. 

To run evaluation on the classification problem formulation of the problem, run `src/eval/classification_problem.ipynb`.

### ML and Statistical Analyses for Climate Variables and Topographic Features
`src/wildfire_modelling_climate_data.ipynb` contains the code for running and evaluating our baseline models only on climate variables. Starting from the section titled **# Statistical Analysis of Fire vs Non-fire Features**, you'll be able to fetch the primary dataframes we curated and integrated earlier in the notebook, and run all relevant ML and statistical analyses.

`src/augmented_feature_engineering.ipynb` contains the code for evaluating neural networks for multivariate regression integrating climate variables with topographic features.

