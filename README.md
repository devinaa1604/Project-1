# PROJECT 1

![](https://images.dwell.com/photos-6488407258118639616/6651031535077519360-large/a-fire-pit-between-two-wings-of-the-home-encourages-outdoor-living.jpg)

## AIM
Our aim was to make a model of housing prices that mimic the infamous Boston Housing Data but on a macro level. We wanted to use Multiple Linear Regression in order to predict the housing prices and make an interactive dashboard which tells the top 25 cities in US for home investors in the next 5 years.

## METHODOLOGY
To achieve this, we started with looking at data sets of variables that could possibly have a correlation with housing returns such as:
  1. Income
  2. Education
  3. Migration
  4. Tax environment
  5. Crime Rates
  6. Environmental Factors

Our data source ranged from:
  1. Kaggle
  2. Zillow
  3. QuandL
  4. Economic Research Service: United States Department of Agriculture
  
## DATA
### Migration Data

### Crime Data

### Problems with data
As we got aquatinted with the terms such as FIPS and CBSA codes, we realized that it is much difficult for us to find the data that matches these county and MSA codes and along with that we needed the data to be in the same time frame, with all yearly data in a format that can be used to run regressions. Therefore, we moved to our alternate plan. 

### Regression data
This data was aquired from "Economic Research Service: United States Department of Agriculture" which followed FIPS (so data was for all the counties in the USA) and it ranged from 2014-2019 (yearly data for each county). The data was then cleaned to after joining the dataframes and remove null values to eventually end up with 18840 data points in the regression. Our final variables were: Population, Unemployment and Net Migration

## MULTIPLE LINEAR REGRESSION
### Scaling
Data was scaled using the MinMax Scaler which first standardizes the data and then normalizes it. This allowed us to make the values comparable with each other as they ranged from 0-1. 

### Correlation
This allowed us to see that none of the variables were highly correlated with each other, eliminating the possibility of heteroskedasticity. We saw that population_estimator is highly correlated with housing prices however, the other two variable are not. We chose to still keep all the variables since we were very limited bu our data. We ran paiplot to see the relationships graphically which all indicated no defined relationship between housing prices and unemployment and net nigration. 

### Regression
We partitioned the data at 20% split and saw that except the unemployment coffecient, all others were statistically significant. The R^2 value was 0.98 which was quiet high and means that 98% of the error is explained/accounded by the model. 
The we fit the training set on the test set which gave us a good fit but that could be attributed to a high R^2 value which isnt very conclusive either. 
The MSE was at 1.5 which shows that 98.5% of the model is accurate however, based on the lack of data and significant coffecients, we were unable to form a predictive model. 

## IMPLICATIONS AND CONCLUSION
1. Our biggest challenge was data:
  i. Find appropriate data for each variable and be able to join them to make one useful data set that can be used for regression and prediction
  ii. Find the data for such macro economic variables could be gorverment data which isnt easily available to us
  iii. Because of lack of data, we had few variables and had to compromise with our regression
  
2. Further work:
    - Include more variables which are better correlated with the target variable and could yield a model that can be used for prediction
    - We could use other models such as Logistic regression model that allow for time series analysis and autoregressive models could maybe fit the data better by          using a lagged value.
