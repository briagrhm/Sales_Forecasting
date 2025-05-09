# Sales_Forecasting
## Prophet Overview 
Creating a sales forecasting model using Prophet because of the features that allow sasonality as well as holiday effects to be taken into account. Prediction is looking for the amount of sales each month. Data pool is very small and may need more data points to be more accurate. the yhat provided by Prophet provides lower and uppper ranges for the predictions so this can be helpful for month where sales vary. 
In prophet the prediction method assign a future predicted value that is named yhat, once historical data is passed in it will provide an insample fit. The forecast object creates a new dataframe that will include the predicion column (yhat) along with columns for components and uncertainty intervals. Prophet_plot_components allows you to see the forecast broken down into trend, weekly seasonality, and yearly seasonality as well as holidays if you include them. 
 
- ds = the dates 
- yhat = average prediction column 
- yhat_lower = lower avergae prediction column 
- yhat_upper = upper average prediction column 

Helpful links:https://www.kaggle.com/code/prashant111/tutorial-time-series-forecasting-with-prophet
https://facebook.github.io/prophet/docs/quick_start.html#python-api
## ARIMA Overview 
ARIMA stands for AutoRegressive Integrated Moving Average. Three parameters are used to help with this time series model: seasonality, trend, and noise. Labeled as p,d, and q. 
- p incorporates past values and is associated with the auto-regressive aspect.
- d effects the amount of differencing to apply to a time series, this is associated with the integrated part of the model.
- q is associated with the moving average part of the model. 
helpful links:https://www.statsmodels.org/stable/generated/statsmodels.tsa.seasonal.seasonal_decompose.html
https://github.com/anindya-saha/Machine-Learning-with-Python/blob/master/time-series/ARIMA-Forecasting-Electric-Gas-Production.ipynb
## SARIMA 
SARIMA(p, d, q)(P, D, Q, s):
- AR(p): Autoregressive component of order p
- MA(q): Moving average component of order q
- I(d): Integrated component of order d
- Seasonal AR(P): Seasonal autoregressive component of order P
- MA(Q): Seasonal moving average component of order Q
- Seasonal I(D): Seasonal integrated component of order D
- s: Seasonal period
## Excel Helpful links 
https://support.microsoft.com/en-us/office/split-text-into-different-columns-with-functions-49ec57f9-3d5a-44b2-82da-50dded6e4a68
## HyperTuning 
1. n_changepoints is the number of change happen in the data. Prophet model detects them by its own. By default, its value is 25, which are uniformly placed in the first 80% of the time series. Changing n_changepoints can add value to the model.

2. changepoint_prior_scale to indicate how flexible the changepoints are allowed to be. In other words, how much can the changepoints fit to the data. If you make it high it will be more flexible, but you can end up overfitting. By default, this parameter is set to 0.05

3. seasonality_mode There are 2 types model seasonality mode. Additive & multiplicaticative. By default Prophet fits additive seasonalities, meaning the effect of the seasonality is added to the trend to get the forecast. Prophet can model multiplicative seasonality by setting seasonality_mode='multiplicative' in the model.

4. holiday_prior_scale just like changepoint_prior_scale, holiday_prior_scale is used to smoothning the effect of holidays. By default its value is 10, which provides very little regularization. Reducing this parameter dampens holiday effects

5. Seasonalities with fourier_order Prophet model, by default finds the seasonalities and adds the default parameters of the seasonality. We can modify the seasonalities effect by adding custom seasonalities as add_seasonality in the model with different fourier order.Yy default Prophet uses a Fourier order of 3 for weekly seasonality and 10 for yearly seasonality.

### Hypertuning Link 
https://www.kaggle.com/code/manovirat/timeseries-using-prophet-hyperparameter-tuning#HyperParameter-Tuning-using-ParameterGrid
https://medium.com/@sandha.iitr/tuning-parameters-of-prophet-for-forecasting-an-easy-approach-in-python-8c9a6f9be4e8
