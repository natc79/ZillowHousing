# Zillow Housing Data

This repository contains code to process, construct and visualize some of the key features in the Zillow Housing Kaggle 2017 competition data.  This data is from the first stage of the competition and the main goal for the first stage was to improve predictions on the log error of the z-estimates focusing mainly on exploiting features/variables included in the properties dataset provided by Zillow.  The geographic coverage of the training/properties data includes 3 counties in southern California and contains log-error z-estimates from between 1/2016-12/2016.  The objective for the public competition was to estimate the log-error on test data from 8/2016-12/2016. 

## Code Files

### process_data_zillow.ipynb

This code explores the raw train and properties dataset.  It finds that the many of the variables included in the properties.csv data that contains features of the houses are missing for more than 90 percent of the sample.  Due to the fairly large size the dataset (~1.7GB) the data is initially processed in chunks, rows where more than 50% of the data is missing are eliminated from inclusion in the final dataset, and data are turned into integer or categorical factors where possible to ensure more efficient storage.  In the end the final processed dataset is reduced to 15MB in size.

### create_features_zillow.ipynb

This code explores some basic visualizations of the data contained in the Zillow dataset.  A major variable potentially omitted from the data that could be leading to higher than expected log-error estimates could be location specific features that were not captured in the original model.  It concentrates on creating some geographic features that may capture location such as distance to beach front, distance from county border, housing density, and an indicator for whether the property could have unobstructed views.

Given the somewhat short range of the time period for the log-error estimates it seems more difficult to estimate seasonal/time effects that might be related to housing price sales.  More importantly the amount of turnover that occurs in a localized area (or just prior) in a given time period it is not really possible to estimate given the available datasets.  However, seasonality in housing sales and number of houses on the market could also be an important variable omitted from current models.


