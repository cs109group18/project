---
title: Data Challenges & Merging
nav_include: 2
---

Listed below are the gaps that we've identified in the extracted data, alongside the design decisions we made for data preparation.

**Crime Data (FBI Uniform Crime Reporting Program):**

* Some MSA had crime statistics within multiple cities while the others only had one. We decided to define our city features as those that come from the largest city (by population) so that each MSA had one set of city statistics


* Not all MSA had 100% reporting rate of data. For those MSAs that did not have 100% reporting, an estimated total was reported. We used the estimated total rather than the actual variables so that all of our data represented the entire MSA (either actual or estimated).

* MSA names changed over time. For example, the MSA **Fort Walton Beach-Crestview-Destin, FL** got renamed to **Crestview-Fort Walton Beach-Destin** in 2009. We identified **14** such instances and the MSAs were manually corrected in Python.

* Crime data did not have a numeric ID for MSA. We initially considered using a cross-walk to translate the MSA descriptions to IDs but decided otherwise since IDs changed over time. MSA desciptions were a concatenation of the key cities followed by the state name. There were instances where an MSA was part of multiple states.For accurate and unique identification, we created a unique **join_key** for each MSA. To create the join key, we extracted the first city name from the MSA description and concantenated it with the state abbreviation (which was also a part of the MSA description). We then used this **join_key along with year to merge the three data sets** to create one complete data frame for subsequent analysis.

**Census Data:**

We created custom tables at the M.S.A level from the census database and extracted the files in Excel format. These files were merged into a census dataframe, which was later joined back to the Crime Dataset

* Around 4% of MSA descriptions differed from what we obtained from the FBI Database. These cases were manually updated.  

**Lack of Data for Puerto Rico:**

All the MSAs within Puerto Rico had less than 11 years of crime and census data. 40% of them had only 5 years worth of information. Due to lack of data, we decided to narrow down our prediction scope to continental United States.
