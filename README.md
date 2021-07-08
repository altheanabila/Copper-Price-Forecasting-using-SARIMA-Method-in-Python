# Copper-Price-Forecasting-using-SARIMA-Method-in-Python


This time I would like to run SARIMA method in order to forecast the price of copper. The data is downloaded as monthly historical data from yahoo finance in range of 5 years period from Jul 08, 2016 - Jul 08, 2021.


1. We need to import and install related libraries

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic1.png)



2. Entry SARIMAX line of code in order to run SARIMA model

`from statsmodels.tsa.statespace.sarimax import SARIMAX`


3. import the data [Cppr.xlsx](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/Cppr.xlsx) and convert into panda dataframes

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic2.png)



4.  Put Date as index of the data

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic3.png)


5. Replace missing value with mean

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic4.png)


6. Run seasonal decompose code, visualize it. 

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic5.png)


7. After we observed all the graphs, we decided to run it using the order that based on ARIMA model, and the seasonal order is run based on seasonal model.

`model = SARIMAX(df['Adj Close'], order=(2,1,2), seasonal_order=(1,1,1,12))`

`model_fit = model.fit()`



8. Plot the residuals. As we can see the residuals are centered around zero. There is no trend and seasonality in the model and look a like a white noise and we can say that there is information that could be extracted from the dataset.


![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic6.png)


9. Obtain the forecasted values. As we can see the last data available is on July 2021, and we get the forecast start from August

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic7.png)

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic8.png)



10. Obtain the predicted values from the beginning date of the data

![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic9.png)


11. visualize the graph


![textimage](https://github.com/altheanabila/Copper-Price-Forecasting-using-SARIMA-Method-in-Python/blob/main/pic10.png)
