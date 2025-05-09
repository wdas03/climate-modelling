# Wildfire Spread Rate Predictions
Instructions on how to run code.

## Getting Data
First, download the `FIRED CONUS AK V2` dataset from https://scholar.colorado.edu/concern/datasets/fx719p11c?locale=de. All wildfire data originates from here.

**Note** This is a very large download and will require at LEAST 40GB of disk space to uncompress.

Once your data is ready, we format the important data into csv files for easy handling and running ML.

**Be sure to edit all filepaths according to your environment/setup!** We make our data available to all LionMail users at https://drive.google.com/drive/folders/1drGPNF-rHee4apAsOcTFDDLzJKu5N5IH 

### Integrate slope data
Run the `data_integration_slopes.ipynb` notebook and change the file paths accordingly. This will output a csv file with corresponding slope, aspect, and elevation data. For your convenience, the resulting file is `ignition_topography_data.csv`. [Download from Google Drive](https://drive.google.com/file/d/1pr1a_Je8V-NFMvdiVt0EDQ6x99erDUqd/view?usp=drive_link)


### Integrate weather data
Run the `weather.ipynb` notebook and change the API keys and file paths accordingly. To fully recreate, create a subscription with https://open-meteo.com/. With our subscription, we we only had access to data after 01/01/2016, so we prune the original data from ~340k to ~120k rows.

This will allow to make a lot of API calls which is needed as there are over 120000 rows of data to account for. This will output a csv file with corresponding weather data. [Download from Google Drive](https://drive.google.com/file/d/1NFF5LQrX20MmjflPbOWDDDUK1vnGHd-e/view?usp=drive_link)

To combine the slope and weather data, run `merge_weather_and_slope.ipynb`. This will result in a csv file with over 300 features. [Download from Google Drive](https://drive.google.com/file/d/1NFF5LQrX20MmjflPbOWDDDUK1vnGHd-e/view?usp=drive_link)

## Evaluation
To run EDA, run `conus_eda.ipynb`.

To run simple out-of-the-box methods, run `baseline.ipynb` and change the file paths to data accordingly. 

To run evaluation on the classification problem formulation of the problem, run `classification_problem.ipynb`.
