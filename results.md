---
title: Results
nav_include: 6
---


As detailed in our model section, we sought to compare different regression methods in order to determine which would give the best predictive performance. We also wanted to test the hypothesis of whether older years would help or hinder the predictive performance on the most recent year (2016) of our data.

![png](models_files/models_15_0.png)

The figure shows that the autoregressive model had the lowest MSE when the autoregressive model was trained using  2014 and 2015 data (i.e recent years) . In this context, Random Forests and Gradient Boosting do not perform as well regardless of how we tuned the hyperparameters. In the time series context, the test set can be very different from the train and it seems the splits learned for these two methods did not perform well on the 2016 data.

Ridge and LASSO have the lowest MSE on average. Additionally, interestingly both of these models have an initial downward trend before stabilizing which supports the hypothesis that **early years (ie 2007-2009) are not as effective in helping to predict more recent data.** This could be because the relationship between different variables and murder changes over time. In other words, we tend to make better predictions by only examining the relationship between variables and murder closer to 2016.

The Baseline (Auto-Regression) model has a clear downward trend which makes sense given the clear relationship between murder and its lag value. However, when choosing between the two models, we come to the conclusion that **Ridge regression training on 5-6 years preceding the year of interest gives optimal predictive performance.**

## Strengths and Shortcomings

The key strengths in this project were the **wide variety of socioeconomic and demographic features** that we collected for an MSA were available across our entire panel. Furthermore, by **tuning multiple models on different training year ranges**, we got really strong evidence of which models worked best on different year ranges which helped us compare models and test how many training years that you need.

There were several key shortcomings to this project. First, we **restricted our analysis to only the continental United States**. While this was our primary interest, we were still disappointed by the low data availability for Puerto Rico which forced us to remove it from our study. Secondly,  we read a paper that talked about **physical characteristics (number of parks within an MSA, land area etc) being more predictive of murder than socioeconomic data.** However, we could not find any data at all. Additionally, the census data provided a margin of error for each variable. We did not use this in our study.  

## Future Work

If we had additional time, we would adjust the crime variables using the margin of error provided in the census data.

We would also like to include additional state-level features, such as average annual temperature, state-level gun restrictions, legalization of marijuana, availability of police stations etc in our study.

We would like to invest more time in the creation of an ensemble prediction model for time series data.

