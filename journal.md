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
