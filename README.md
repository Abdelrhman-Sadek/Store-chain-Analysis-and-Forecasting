# Store-chain-Analysis-and-Forecasting
<div align="center"> <img align="center" src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS0kHivyrbuw43hgbcGGGmmYcLaNYhryY31LAOXmNX3zXbOOfIGKti1FQ-6fLZ_4oTq_3Y"> /div>
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
