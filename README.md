# datasci-bitcoin-predictor
Time series analysis of (and attempt to predict) 1-day bitcoin returns. ARMA, Regression, and LSTM models.

## Summary
This is my final project for Metis (a data science bootcamp). It includes a scraper & stitcher for Google Trends data and a few different time-series models (ARMA, regression, LSTM). 

The goal is to predict 1-day ahead bitcoin returns based on past data (changes in bitcoin price, bitcoin volumes, alt-coin prices, financial indices, google trends). A great model would enable a trading strategy, but it would also be interesting to see which factors are most predictive.

The volatility in Bitcoin price makes this a tough problem, but also a good environment to try out time series techniques.

## Files:
#### Code
* **Bitcoin_EDA_ARMA.ipynb** - Time series modeling to predict price using "traditional" ARMA and trend / season / noise decompositions on past price only
* **Bitcoin_EDA_Classification.ipynb** - (Tentative / work in progress) Time series modeling treating prediction as a classification of next day direction only (up or down)
* **Bitcoin_EDA_Regression_v3.ipynb** - Time series modeling to predict price using regression (linear + trees) and LSTM on multiple features
* **Bitcoin_Scrape_Google_Trends.ipynb** - Google trends "scraper" using Pytrends + logic to connect daily relative values using weekly relative index (Google only provides daily values up to 90-day periods, longer periods are weekly data only).

#### Docs
* **Bitcoin_Price_Pres.pdf** - Presentation slides

## Results
I started with a baseline model that predicted the training mean for all test cases, and a baseline ARMA that attempted to predict future price based only on past price. The R-square was slightly negative, indicating that baseline wasn't able to explain any of the variance in next-day returns. 

Next, I looked for signal by adding more potentially predictive features and by trying more complex models that might better represent relationships in the data. However, I found that 1-day ahead future returns aren't predictable based on the features and models I used. The models weren't able to do any better than a naive baseline of predicting the mean (R^2 ~ 0). 

As additional evidence, see slide 8 in the presentation. When plotting out the bias-variance tradeoff (R-square on test & training sets), it is fairly apparent that despite better training set fit, test set fit begins decreasing right away as complexity is added over the baseline model - showing that we are indeed overfitting and there is little signal to be found. In the case of LSTM, I believe there weren't enough data points to properly train the model.

In the end, I learned a lot about time series models including statistical single variable approach, regression-based ML, and recurrent network based prediction. I'm looking forward to applying these techniques to other, less volatile time series.
