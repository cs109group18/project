---
title: Results
nav_include: 6
---

### Placeholder for findings

As detailed in our model section, we sought to compare different regression methods in order to determine which would give the best predictive performance. We also wanted to test the hypothesis of whether older years would help or hinder the predictive performance on the most recent year (2016) of our data.

![png](models_files/models_15_0.png)

The figure shows that the autoregressive model had the lowest MSE when the autoregressive model was trained using 2014 and 2015 data. In this context, Random Forests and Gradient Boosting do not perform as well regardless of how we tuned the hyperparameters. In the time series context, the test set can very different compared to the train and it seems the splits learned for these two methods did not perform well on the 2016 data.