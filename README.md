# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 2: Regression Challenge - Predict the price of homes at sale for the Ames Iowa Housing dataset 

### Henri Oei, DSIF2 - Singapore

## Problem Statement

Homeowners struggle to identify what aspects or features of their home are vital to determining the value of their homes.

## Executive Summary

The Ames Iowa Housing dataset included a lot of features that may or may not have an impact in predicting sale price, which is what we want to find out through our analysis. Data cleaning took some time as there were a lot of missing values and the challenge was to figure out the appropriate variable replacement for them. Our initial model included all the features that was provided except some that was dropped because it had no linearity towards our target, sale price. We performed the following models:

1. KNN Regression
2. Linear Regression
3. Ridge Regression
4. Lasso Regression
5. ElasticNet Regression
6. OLS Regression 
7. MSE for Result Validation and to test for fit

The MSE scores were average, with Lasso Regression having the best score of 25,722. However, all our models turn out to be overfitted by a lot.

Thus, we decided to take a different approach and single out 10 features that we want to use for our final modeling. We decided to hand pick out of the top 20 lasso coefficients that came out to be the following:

1. Ground Living Area
2. Overall Quality
3. Fireplaces
4. Neighborhood Stone Brook
5. Neighborhood Northridge Heights
6. Screen Porch
7. Garage Cars
8. Full Bath
9. Basement Full Bath
10. Overall Condition

The MSE score for the Lasso Regression came up to be higher than previously with a score of 35,219. However, the model is not overfitted (0.0138%).

## Conclusions and Recommendations

After extensive research we have concluded that the model with the top 10 lasso coefficients is our best model with an MSE that is not overfitted. 

For our homeowners who wish to increase their sale price, they should focus on the following:

1. Including full bathrooms in the basement and above ground
2. A garage that fits at least 3 cars seems to be the popular choice
3. Remodel your home to include a screen porch
4. Include a fireplace, but that is optional
5. Having the first floor elevated above ground
6. Make sure that the walls, floors, ceilings, bathrooms, kitchen, stairs, doors, are not wornout because a high overall quality score will definitely increase your chances for a higher sale price.
7. Neighborhoods such as Northridge Heights and Stone Brook tend to fetch a higher sale price if you consider buying a new home in the near future.

## Data

### *Source*

We are provided datasets of Ames Iowa Housing dataset (train & test):

Train Dataset:
* Columns - 81
* Rows - 2051
* Float - 11
* Int - 28
* Obj - 42
* Missing Values - 9822

Test Dataset:
* Columns - 80
* Rows - 878
* Float - 3
* Int - 35
* Obj - 42
* Missing Values - 4171

### *Data Cleaning*

The following actions were taken for data cleaning:

1. Replaced values that are null to 0
2. Created Dummy variables for features that are not numeric
3. Dropped columns that are not linear to sale price

### *Data Dictionary*

|Feature|Type|Dataset|Description|
|---|---|---|---|
|SalePrice|float|top10_hand_picked_features|Sale price $$| 
|Gr Liv Area|float|top10_hand_picked_features|Above grade (ground) living area square feet|
|Overall Qual|int|top10_hand_picked_features|Rates the overall material and finish of the house|
|Fireplaces|int|top10_hand_picked_features|Number of fireplaces|
|Neighborhood_StoneBr|int|top10_hand_picked_features|Physical locations within Ames city limits|
|Overall Cond|int|top10_hand_picked_features|Rates the overall condition of the house|
|Screen Porch|int|top10_hand_picked_features|Screen porch area in square feet|
|Neighborhood_NridgHt|int|top10_hand_picked_features|Physical locations within Ames city limits|
|Garage Cars|float|top10_hand_picked_features|Size of garage in car capacity|
|Full Bath|int|top10_hand_picked_features|Full bathrooms above ground|
|Bsmt Full Bath|float|top10_hand_picked_features|Basement full bathrooms|