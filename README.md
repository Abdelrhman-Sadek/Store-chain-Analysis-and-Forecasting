# Store-chain-Analysis-and-Forecasting
![image](https://user-images.githubusercontent.com/94745919/236902695-59ba29d7-0e95-4cc1-b6a6-525928ea0142.png)

## Description 
**This is a complete Time_Series store chain analysis the goal was to determine**:

* products at each store of the chain and there promotion at a given date.

* which product family have the most and least sales.

* which store have the most and least sales

* which (city, state, type) have the most and least sales. 

* the trned and seasonalty of the time series and how the data changes over time(weekly,monthly,daily,etc)

* the relationship between sales and (Holidays(Local,Regional),Oil Price) and how big they effects the sales.
* the relationship bettween the time lags  

* How many shop visitors in each day(transactions) and how it effects the sales 
<br/>
then use this informations and train a Hybrid model of Liner Regression and CatBoostRegressor to forecast test_detaset(16 day) of sales for each product family in every store

the acc of the Hybrid model is pretty good (a round 99%)
<br/>
Data Link: 
<br/>
https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview
