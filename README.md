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
![image](https://user-images.githubusercontent.com/94745919/236908531-fd3d279a-25e5-4206-b361-5d1b340a55f4.png)
</br>
Monthly:
![image](https://user-images.githubusercontent.com/94745919/236908420-6716b2b1-bf2f-466c-9d2b-10615816963e.png)
</br>
Week day average sales:
</br>
![image](https://user-images.githubusercontent.com/94745919/236904876-15f187dc-6822-4cc1-b140-c88baf722d5f.png)
</br>
there is an increse of sales every year that indicates a trend variable
</br> 
everyday of the year the sales =0 as shown from "Daily Avg,that means that the market is closed.
</br> 
sales on the weekend the highest of the week and generally low on Thursdays.
</br> 
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
The sales is increasing over the years

### Determine seasonalty
useing the periodogram to determine the seasonalty there is 10 different seasonalties Annual (1) Semiannual (2) Quarterly (4) Bimonthly (6) Monthly (12) Biweekly (26) Weekly (52) Semiweekly(104) Daily(365) Time of day
![image](https://user-images.githubusercontent.com/94745919/236909383-ed6ff18f-3718-41ee-b84f-0866cc5f3c10.png)
</br>
The periodogram it suggests a strong weekly seasonality
</br>
![image](https://user-images.githubusercontent.com/94745919/236909762-f873d2a5-0e1c-4514-b557-1df82d7bb79d.png)
</br>
A lag plot of a time series shows its values plotted against its lags. Serial dependence in a time series will often become apparent by looking at a lag plot.
</br>
Using plot_pacf to see the corrlation between 12 lags only:
![image](https://user-images.githubusercontent.com/94745919/236910235-c31073a6-c03b-477a-a25b-9093406898e4.png)
</br>
plot_pacf show a strong corrlation between lags (1 3 5 6 7 8 and 9) so we will be useing these lags in training

### Holidays
After removing the transfered data so it dont causes mislead the sales showed s strong corlation with sales:
![image](https://user-images.githubusercontent.com/94745919/236911536-19e4502e-7ea8-4beb-a0b9-73c6eccf1431.png)
![image](https://user-images.githubusercontent.com/94745919/236911573-cb59cbfe-e4ac-4d07-8e64-7b3b7565d6fa.png)
</br>
Comparing Avg_sales on holidays vs on work days
![image](https://user-images.githubusercontent.com/94745919/236911945-1866f144-9099-488f-aec9-e3ef6b1b3308.png)
</br>
Sales is significantly higer in **Holidays** 

### Oil prices 
![image](https://user-images.githubusercontent.com/94745919/236913120-0bab6331-3b13-4eb5-a1fc-d89157dd3e4e.png)
</br>
The oil price have a negative corrlation with sales the lower oil price is the more purchasing power for the customers.

### Stores
![image](https://user-images.githubusercontent.com/94745919/236914165-7483bbcb-6231-4668-96fb-8fe8c3512983.png)
the plots shows:
</br>
* the best city sales is 'Quito' with over than 500 and percentage of 9.4% of total sales the lowest city sales is 'Puyo' with below 100 sales with only 1.2%
* the order of best store type sales is (A,over(700),38% of sales),(B,over(300),19% of sales),(E,(300),17% of sales),(C,over(200),10.7% of sales)
* the highest sale state is 'pichincha' with 13.2% of the sales and over 500 while the other states are close in sales with the highest percentage of 8.7 ('tungurahua') and the lowest is 'pastaza' 1.8%

* the highest store culster is 5 with over then 1000 and percentage of 16%

### Transations


</br>
then use this informations and train a Hybrid model of Liner Regression and CatBoostRegressor to forecast test_detaset(16 day) of sales for each product family in every store

the acc of the Hybrid model is pretty good (a round 99%)
<br/>
Data Link: 
<br/>
https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview
