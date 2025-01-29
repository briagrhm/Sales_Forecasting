# Sales_Forecasting
## Overiview 
Creating a sales forecasting model using Prophet because of the features that allow sasonality as well as holiday effects to be taken into account. Prediction is looking for the amount of sales each month. Data pool is very small and may need more data points to be more accurate. the yhat provided by Prophet provides lower and uppper ranges for the predictions so this can be helpful for month where sales vary. 
In prophet the prediction method assign a future predicted value that is named yhat, once historical data is passed in it will provide an insample fit. The forecast object creates a new dataframe that will include the predicion column (yhat) along with columns for components and uncertainty intervals. Prophet_plot_components allows you to see the forecast broken down into trend, weekly seasonality, and yearly seasonality as well as holidays if you include them. 
 
- ds = the dates 
- yhat = average prediction column 
- yhat_lower = lower avergae prediction column 
- yhat_upper = upper average prediction column 

Helpful links:https://www.kaggle.com/code/prashant111/tutorial-time-series-forecasting-with-prophet
https://facebook.github.io/prophet/docs/quick_start.html#python-api
