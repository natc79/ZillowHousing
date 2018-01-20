# Zillow Housing Data

This repository contains code to process, construct and visualize some of the key features in the Zillow Housing Kaggle 2017 competition data.  This data is from the first stage of the competition and contains log error of the z-estimates.  The main goal of the competition was to improve predictions on the log error of the z-estimates.

## Code Files

### process_data_zillow.ipynb

This code explores the raw train and properties dataset.  It finds that the many of the variables included in the properties.csv data that contains features of the houses are missing for more than 90 percent of the sample.  Due to the fairly large size the dataset (~1.7GB) the data is initially processed in chunks, rows where more than 50% of the data is missing are eliminated from inclusion in the final dataset, and data are turned into integer or categorical factors where possible to ensure more efficient storage.  In the end the final processed dataset is only 15MB in size.

### create_features_zillow.ipynb

This code explores some basic visualizations of the data contained in the Zillow dataset.  It hypothesizes that a major variable omitted from the data that could be leading to higher than expected log-error estimates could be location specific features that were not captured.  It concentrates on creating some geographic features that may capture location such as distance to beach front, distance from county border, and housing density.

