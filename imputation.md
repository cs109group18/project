---
title: Imputation
nav_include: 4
---
We first decided that a variable needed to be there **> 75%** of the time for us to impute it. The threshold of 75% or greater was set to obtain realistic, reliable and complete imputations. Intuition and the findings from EDA drove the design of our imputation strategy. We thought that the best way to impute data is to use **a simple linear interpolation by MSA**. This approach attempts to take advantage of the fact that a variable should be highly related to itself in the past and future within the MSA.

We ran each of the imputation strategies over our data and compared downstream model performance. **Imputation Strategy # 1 yielded higher test set performances**, so this became our default.

### Approach 1

This equation is what will be used to impute a variable denoted Y<sub>t</sub> for year t

 $$Y_t = B_0 + B_1 Y_{t-1} + B_2 \frac{Pop_t}{Pop_{t-1}} + B_3 MSA_i $$
 
 We will leverage the variable value from the previous year (if available) and iteratively fill Y<sub>t</sub> until the variable is completely filled. For example - Consider a situation where a variable has missing values for both 2008 and 2009. We first predict the variable value for 2008 using 2007. The iputed value of 2008 is then used to estimate the missing value of 2009. Please note that we also do a population adjustment for growth. 
 
 
If the variable has missing values for all past years before year t, we use the observation for the year after t for imputation. We weigh the value using a simple population adjustment:

 $$Y_t = Y_{t+1} * \frac{Pop_t}{Pop_{t+1}} $$
 
### Approach 2

 
 $$Y_t = Y_{t-n/t+n} * \frac{Pop_t}{Pop_{t-n/t+n}} $$

In this second approach, we will do simple population adjustment using the nearest available year. Here, n represents the number of missing periods we have to go to find the first non-missing data. First, we will go to **first** lag period (one year before). If that is missing, we will go to year after. If data is missing for the nearest years (both lag and lead), we then identify two years before the year in question. If that is missing, we attempt an interpolation using the two years after.

### Imputation of Carson City Data

Carson City MSA was missing crime rate statistics for all years. We used MSA-wide imputation to address this situation. It was also missing employment rate for all 11 years. To solve this scenario, we leveraged the Bureau of Labor Statistics data to manually impute employment rates for all years