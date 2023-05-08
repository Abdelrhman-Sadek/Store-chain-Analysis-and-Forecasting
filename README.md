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
## Data Analysis
before beginning with the analysis frist we need to know the skewness of the data:
![image](https://user-images.githubusercontent.com/94745919/236903584-14ce3266-367b-4510-8202-7bd2fd831aaa.png)
</br>
the sales is highly positive skewned,the given distribution is shifted to the left and with its tail on the right side.
</br>
Yearly average sales by : day,week,month 
</br>
Daily:
![image](https://user-images.githubusercontent.com/94745919/236904133-b716fad4-daad-4ee7-a1dc-52b1639c1d7c.png)
</br> 
Weekly:
![image](https://user-images.githubusercontent.com/94745919/236908045-d955026d-35c1-49eb-a84e-bc3cb3f039be.png)
</br>
Monthly:
![image](https://user-images.githubusercontent.com/94745919/236908105-9bbbd184-2385-4b6e-80b9-a28ff66fde79.png)

</br>
Week day average sales:
![image](https://user-images.githubusercontent.com/94745919/236904876-15f187dc-6822-4cc1-b140-c88baf722d5f.png)
there is an increse of sales every year that indicates a trend variable
</br> 
everyday of the year the sales =0 as shown from "Daily Avg,that means that the market is closed.
</br> 
sales on the weekend the highest of the week and generally low on Thursdays.
</br> 
Identifies the type of famliy product sold:
![image](https://user-images.githubusercontent.com/94745919/236906110-08262bb1-9b5a-47e0-9ebe-04de06f1523f.png)
</br>
The best family products sell are:  ['GROCERY I', 'BEVERAGES', 'PRODUCE', 'CLEANING', 'DAIRY']
</br>
The worst family products sell are:  ['MAGAZINES', 'HARDWARE', 'HOME APPLIANCES', 'BABY CARE', 'BOOKS']
</br> 
Identifies how the sales is going with each store:
![image](https://user-images.githubusercontent.com/94745919/236906570-e4cc381d-cc3a-4a7f-9b86-e8beff554313.png)
</br>
Best stores sales are : [44, 45, 47, 3, 49]
</br>
Worest stores sales are : [35, 30, 32, 22, 52]
</br>
### Determine the trend
I choose a window of 365 days since this series has daily observations to smooth over any short-term changes within the year so that only the long term changes remains 
![image](https://user-images.githubusercontent.com/94745919/236907318-556012ca-cc12-436e-b259-e940841f8e6d.png)


</br>
then use this informations and train a Hybrid model of Liner Regression and CatBoostRegressor to forecast test_detaset(16 day) of sales for each product family in every store

the acc of the Hybrid model is pretty good (a round 99%)
<br/>
Data Link: 
<br/>
https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview
