---
title: Data Sources
nav_include: 2
---

## Data Sources

We used **three** primary sources for out project. For all of our sources, we gathered data for the years **2006 - 2017**. Our observational unit was **Metropolitan Statistical Area (MSA).** An MSA is defined to be a geographical area with high population density.

### Data Source 1: FBI Uniform Crime Reporting (UCR) Program

We **automated** the extraction murders and man-slaughter data from the FBI database for the years 2006 - 2017.**Table 1** lists the features provided in the FBI database.

|          Name          |
|:--------------------------------:|
| Violent Crime                     |
| Murder + Non-negligent Manslaughter|
| Forcible Rape               |
| Robbery                  |
| Aggravated Assault            |
| Property Crime           |
| Burglary           |
| Larceny-theft                |
| Motor Vehicle Theft                |
| Population of MSA         |
| Population of Largest city within MSA          |

The crime variables available from Table 1 were available in three separate forms: number for entire MSA, number within the largest city of the MSA, and the number across the MSA per 100,000 individuals (a rate).

*URL: https://ucr.fbi.gov/ucr-publications*

### Data Source 2: United States Census Bureau (UCSB)

We obtained demographic data for each MSA from the USCB.  We used our EDA (Exploratory Data Analysis), intuition, and the provided Glaeser paper to identify the features in scope. **Table 2** list the names, definitions, and table numbers for which we got census data.


|          Feature Name          | Feature Definition | USCB Table Number |
|--------------------------------|---|----------------------------------------------------------------------|
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |
| Placeholder 1                     | Description 1 | Table 1 |


We selected these variables because data were widely available (by year and by MSA) and we wanted to try to collect a range of economic, gender, racial, and age features to get a diverse array of variables about an MSA.

*URL: https://factfinder.census.gov/*

### Data Source 3: Bureau of Economic Analysis (BEA)

The data on income from UCSB were mostly missing and thus unusable.  Instead, we looked to the BEA which provided **real per-capita GDP**, which can be seen as a metric to measure an MSA aggregate economic activity.  The reason we chose real per-capita GDP are two-fold. Per-capita GDP is better than GDP for our purposes because it adjusts for population. Otherwise, larger MSA will always have larger GDP due to more people and resources. Secondly, real per capita GDP was chosen to control for inflation. Our GDP measure is in 2005 dollars for all years so that comparisons between years is due to actual changes rather than inflation

*URL: https://www.bea.gov/iTable/iTable.cfm?ReqID=70#reqid=70&step=1&isuri=1&7003=1000&7004=naics&7035=-1&7005=1&7006=xx&7001=21000&7036=-1&7002=2&7090=70&7007=-1&7093=levels*
