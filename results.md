---
title: Results
nav_include: 6
---


As detailed in our model section, we sought to compare different regression methods in order to determine which would give the best predictive performance. We also wanted to test the hypothesis of whether older years would help or hinder the predictive performance on the most recent year (2016) of our data.

![png](models_files/models_15_0.png)

The figure shows that the autoregressive model had the lowest MSE when the autoregressive model was trained using  2014 and 2015 data (i.e recent years) . In this context, Random Forests and Gradient Boosting do not perform as well regardless of how we tuned the hyperparameters. In the time series context, the test set can be very different from the train and it seems the splits learned for these two methods did not perform well on the 2016 data.

Ridge and LASSO have the lowest MSE on average. Additionally, interestingly both of these models have an initial downward trend before stabilizing which supports the hypothesis that **early years (ie 2007-2009) are not as effective in helping to predict more recent data.** This could be because the relationship between different variables and murder changes over time. In other words, we tend to make better predictions by only examining the relationship between variables and murder closer to 2016.

The Baseline (Auto-Regression) model has a clear downward trend which makes sense given the clear relationship between murder and its lag value. However, when choosing between the two models, we come to the conclusion that **Ridge regression training on 5-6 years preceding the year of interest gives optimal predictive performance.**

### Strengths and Shortcomings

