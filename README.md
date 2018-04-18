# datasci-bitcoin-predictor
Time series analysis of (and attempt to predict) 1-day bitcoin returns

## Summary
This is my final project for Metis (a data science bootcamp). It includes a scraper & stitcher for Google Trends data and a few different time-series models (ARMA, regression, LSTM). 

The goal is to predict 1-day ahead bitcoin returns based on past data (changes in bitcoin price, bitcoin volumes, alt-coin prices, financial indices, google trends). A great model would enable a trading strategy, but it would also be interesting to see which factors are most predictive.

The amount of variance in Bitcoin pricing makes this a tough problem, but also a good environment to try out time series techniques.

## Files:
#### Code
* **Bitcoin_EDA_ARMA.ipynb** 
* **Bitcoin_EDA_Regression.ipynb**
* **Bitcoin_Scrape_Google_Trends.ipynb**

## Results
Despite trying many different features & models, I wasn't able to find signal in the data! The models weren't able to do any better than a naive baseline of predicting the mean (R^2 = 0).
