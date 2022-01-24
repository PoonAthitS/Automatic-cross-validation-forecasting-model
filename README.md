# Automatic cross validation forecasting model
* Written by: [Poon Athit S. ](https://www.linkedin.com/in/athit-srimachand/)
* Technologies: R, cross-validation, Error measures, forecast
## 1. Introduction
The purpose of this project is to develop an automatic models suitable for batch forecasting (large amount of time series) based on monthly M3 Competition data sets which is expected to be one of the standard time-series datasets used to demonstrate various aspects of forecasting in numerous studies. It uses automatic exponential smoothing and automatic ARIMA modelling techniques in conjunction with the model selection strategy and cross-validation methodology to achieve the highest possible accuracy for the error measures chosen. The model is advantageous to users or organisations when a large number of monthly time series are aimed to be predicted over an 18-month horizon. 

## 2. About the model
The developed automatic model uses the model selection strategy which chooses from 2 models between automatic ETS and ARIMA; however, in practice, more models can be further added if necessary. Meanwhile, rolling-origin, expanding-window are selected as the strategy for the cross validation due to the characteristics of datasets. 
<br /> <br />
<img src="https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/IMAGES/Process%20of%20the%20model%20selection.png?raw=true" width="650">

The process of forming the model begins with fitting the time series selected from 130 series using automatic ETS and ARIMA modelling methods. After that, each model's significant parameters are gathered and used in the subsequent process. The length of each validation is determined to be 18 months to correspond to the forecast horizon specification. The number of cross-validation steps is also then calculated based on the length of the time series, which is either 6, 12, 24 or 36 steps. Following this number of steps, the training and validation data are properly separated from the time series to fit the ETS and ARIMA models using previously obtained parameters. MAPE error measure is then used to determine the models' accuracy when forecasting and comparing to validation data. After repeating the preceding steps for a number of times as the number of cross-validation steps, the average MAPE for each model is compared. The model with the lowest mean of MAPE, either ETS or ARIMA, is then chosen to perform the forecast accuracy evaluation in the next step. Meanwhile, this entire process is repeated for each of 130 series.


## 3. Key findings
The forecast performances of the developed automatic model is studied by the selected error measures along with other 2 automatic models and 3 benchmarks: auto ARIMA, auto ETS, naïve, seasonal naïve and damped exponential smooth respectively.

### 3.1 Performance of the model presenting by multiple Error measures
<img src="https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/IMAGES/The_results_of_each_forecasting_model_across_different_horizon_ranges.png?raw=true" width="400">
<img src="https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/IMAGES/Average_MASE_of_the_developed_automatic_model_across_different_horizons.png?raw=true" width="500">

the results indicate that, on average, the developed automatic model from this project performs as the best model across different ranges of horizons and error measures. However, MAPE and MdAPE demonstrate that auto ETS produces superior results in the short-term forecast horizon.

### 3.2 Performance of the model in different categories of data
<img src="https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/IMAGES/Methods_which_give_the_best_result_for_each_category_and_horizon_by_MASE.png?raw=true" width="550">
From the table, the results confirm the last analysis that, overall, the developed automatic model perform outstandingly when compared to other models. However, when focusing on each category, the result varied. Auto ETS model is concluded by the majority that it is the best model for MICRO and OTHER while auto ARIMA is the best model for the INDUSTRY category. On the other hand, MASE and AvgRelMAE suggest the developed model for MACRO and DEMOGRAPHIC categories which is opposed to the MAPE and MdAPE’s recommendation.

### 3.3 Example of the automatic cross validation forecasting model
<img src="https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/IMAGES/18-month_forecast_of_unglazed_brick_shipments.png?raw=true" width="500">
The example of the forecasts from the model is produced as the above image, which is the ungrazed brick shipment 18-month forecasting.

## 4. About the programming

### 4.1 Files
The model is developed in [R markdown notebook.](https://github.com/PoonAthitS/automatic-cross-validation-forecasting-model/blob/main/Automatic_cross_validation_model_M3Comp.rmd)

### 4.2 Data
Thr data is from the 3003 time series from the M3 competition which embeded in package Mcomp

### To learn more about Poon Athit S., visit his [LinkedIn profile](https://www.linkedin.com/in/athit-srimachand/)

All rights reserved 2022. All codes are developed and owned by Poon Athit S. or the metioned team member(s). If you use this code, please visit his LinkedIn and give him a skill endorsement in Data analytics and the aforementioned coding technologies.
