# February 21, 2025
We sat down and discussed to finalize the general direction we wanted to go in. We decided that we did not want to focus on anything too complex otherwise we could lose sight of the project and what we wanted to focus on. To this, we were interested in focusing on disease prediction.

# February 23, 2025
Discussed multiple papers we looked at over the past days and decided to focus on a really solid grape dataset which also includes environmental variables. With regards to ML technique, we want to look at supervised techniques such as random forests, and LSTM networks to capture both spatial-temporal patterns and non-linear interactions in the data.

Papers and datasets we've looked at:
* https://www.sciencedirect.com/science/article/pii/S2352938524000958
* https://www.nature.com/articles/s41467-021-25257-4
* https://paperswithcode.com/dataset/plantdoc
* https://paperswithcode.com/dataset/plantvillage
* https://paperswithcode.com/dataset/diamos-plant 
* https://www.sciencedirect.com/science/article/pii/S2352340923009861
* https://pmc.ncbi.nlm.nih.gov/articles/PMC11190471/ 

# March 7, 2025
Discussed with researcher in Climate school who is working on wildfire simulations. He suggested https://landfires.gov/data for good data and shared some of his experience on working on these types of projects. Main challenge with data is going to be combining multiple sources and aligning.

# March 10, 2025
Revised project proposal after working with grape disease dataset and assessing its unviability.

Went through bunch of datasets on Landfire.gov and FIRED providing data relating to topography, land terrain, various weather conditions, and fire progressions for various regions - looked particularly at opportunities to synchronize data for overlapping spatial regions between the two sources.

New project direction: wildfire simulations + prediction. Updated in abstract.md file.

EDA done for MERRA global temperature + wind speed/flow data, FIRED data for wildfire occurences in CONUS, and elevation data for CONUS so far.

# March 21, 2025
For reference, this paper provides a good amount of sources for data. https://www.sciencedirect.com/science/article/pii/S2666719324000244. We continue to work on data wrangling and alignment.

# March 23, 2025
Because the CONUS dataset is gigantic and my personal computer can't handle it, I decided to do some explorations of objective 1 (from abstract) and play around with some dummy data to predict wildfire spread. If this yields fruitful, I think we can continue to explore this route and see how simulations go. 

For more thorough simiulations, we will need to actually factor in variables like wind change (from MERRA data) to represent a more realistic scenario.

# March 30, 2025
Worked more on data integration with elevation and slope data, and mainly on problem statement 1 of abstract.md. Made some more progress with data curation and planning to test a few ML models.


# April 2, 2025
Finally got integrated ignition data after hours of running conus notebook. Next steps is to do somebaseline evaluations.

# April 7, 2025
Used the CSV produced from elevation data to see how that performs. As expected it performed really poorly -- we need to account for other factors such as slope and aspect data. Elevation is relevant but does not account for much.

# April 8, 2025
Due to the poor performance of only considering elevation data, we update our integration pipeline to consider slope and aspect data. We hope that taking this route will give us promising results.

# April 11, 2025
Tested with newly acuired slope and aspect data -> unfortunately using just our exisitng out-of-the box methods didn't prove to be too much different. We plan to explore more into the data and potentially changing our methodology.

# April 16, 2025
Integration of additional slope aspect data to augment the slope percent and degree data (providing directionality of slopes for the ML models).


# April 21, 2025
Start on reports and ran some more tests using modified CONUS dataset.

# April 27, 2025
After some discussion on our current results, which did not prove to be too fruitful, we discussed other approaches. First, we will try to reframe regression prediction as classification problem. Instead of predicting continuous values, we categorize fire spread rates or total area of fire burned into severity categories, i.e. low, medium, high and run classification in same exact way. After looking at the dataset, we see most ranges fall between 0.1 and 1.0 (with most being around ~0.2 km^2/day). With this we start with boundaries of 0.1 for low severity and 1.0 for high severity.

One thing to note from running tests with basic classification methods (naive bayes, etc.) is the class imbalance. As previously noted, nost values for fire spread rate are around 0.2.


# May 1, 2025
After some feedback from professor, we decided to steer away from one-hot encoding of categorial variables as it would degrade tree-based method performance.

# May 5, 2025
Wanted to use some unsupervised techniques like PCA to see which features are contributing to the variance the most.

# May 6 + 7
Using the data from the `fired_conus_ak_2000_to_2024_events.csv` file, we can use the ignition coordinates and event dates to make calls to the Open Meteo API to get information on associated weather events such as precipitation, sun exposure, and humidity.

# May 8 + 9
Even with the new data, we are still getting negative R^2 scores despite trying various methods. I think the conclusion is that fire spread rate prediction is a very tricky topic to tackle. A part of it probably has to do with the data skewedness.

# May 10
Ran more analysis with new augmented data. Tested Deep Learning approaches and new two-week forcasting binary classifcation formulation.
