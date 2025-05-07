# Wildfire Spread Rate Predictions
Instructions on how to run code.

## Getting Data
First, download the `FIRED CONUS AK V2` dataset from https://scholar.colorado.edu/concern/datasets/fx719p11c?locale=de 

*Note* This is a very large download and will require at LEAST 40GB of disk space to uncompress.

Once your data is ready, we format the important data into csv files for easy handling and running ML.

### Integrate slope data
Run the `data_integration_slopes.ipynb` notebook and change the file paths accordingly. This will output a csv file with corresponding slope, aspect, and elevation data. For your convenience, the resulting file is `ignition_topography_data.csv`.

### Integrate weather data
Run the `weather.ipynb` notebook and change the API keys and file paths accordingly. This will output a csv file with corresponding weather data.

## Evaluation
