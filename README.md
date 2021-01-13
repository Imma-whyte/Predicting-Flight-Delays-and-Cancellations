## Predicting-Flight-Delays-and-Cancellations

Group Members: Immaculate Ezeogbo, Melissa Hartwick, Jenarth Jegatheeswaran, Karanbir Singh Kamboj, Monica Sanchez, Reece Weigel


#### Introduction
COVID-19 upended the global airline industry. The sector, which accounts for 4% of the world’s GDP, could face an approximate loss of close to $400B in revenues from passenger flights. 

Only recently, airlines have started to reopen their boarding gates to travellers with the announcement of a vaccine. As airlines begin to do so, we felt it was timely to use our skills to build a prediction model which would help airlines better predict flight delays and cancellations, two of the top pain points for airline customers. 



#### Objectives of the Analysis
The objective of our analysis was to accurately predict flight delays and cancellations prior to departure. Due to the vast number of scheduled flights globally on any given day, as well as the complexity in understanding on-time performance variability across countries, we focused the scope of our analysis on domestic passenger flights in the United States. 



#### Data Preparation
[Airline On Time Performance Data](https://www.transtats.bts.gov/Tables.asp?DB_ID=120/)


The dataset used for our analysis is called [Airline On Time Performance Data](https://www.transtats.bts.gov/Tables.asp?DB_ID=120/) Airline 'On-Time Performance Data' (see link above) and is from the Office of Airline Information at the US Bureau of Transportation Statistics. The dataset contains information regarding non-stop domestic flights operated by US carriers that account for at least one percent of domestic scheduled passenger revenues. While the original dataset was available on a monthly basis from October 1987 to September 2020, the dataset was 13GB. Even with our big data tools, this was too big for the community edition of Databricks which has a maximum of 6GB. In the end we had to reduce our dataset to one month of data (January 2019), which still consisted of over 500,000 rows of data and 30+ variables once cleaned and prepared. 


#### Analysis & Model Development
Prior to building our model, we explored the dataset for interesting trends and patterns related to delays and cancellations. Within our dataset there were 50,185 delayed flights (9% of total flights). There were also 16,724 cancelled flights (3% of total flights). The majority of delayed and cancelled flights originated from Chicago. While this is not the busiest airport in the US, there was a major storm in January 2019 which impacted the Chicago area. We hypothesize contributed to the delays and cancellations. 

Throughout our analysis we developed various models to predict three aspects of delays/cancellations: likelihood of delay, length of delay, and likelihood of cancellation. While the dataset we worked with had a lot of informative variables, they may not have been sufficient to build models that can predict delays and cancelations. For example, we were missing weather data, airport congestion metrics, maintenance logs, etc. Based on this, our logistic regression models did not prove to have strong enough predictive power for predicting delays and cancellations, nor did the linear regression model have enough predictive power to predict length of delays. Our final model which used a random forest classifier to predict cancellations, beat all of our other models with a 97% accuracy. We would need to further test this model on other months of data to further validate its predictive power and make sure it is not overfitting the data.
