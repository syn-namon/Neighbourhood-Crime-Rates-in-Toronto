- [Purpose and Overview](#purpose-and-overview)
- [Methodology](#methodology)
- [Project Scope](#project-scope)
- [Data Cleaning](#data-cleaning)
- [Analysis](#analysis)
- [Visualization](#visualization)
- [Conclusion](#conclusion)
- [Credits and Source](#credits-and-source)

# Purpose and Overview

In this project I have performed the analysis for the hystoric data of neighbourhood crime rates in Toronto from 2014 to 2024 and forcasting for the crime volume total in 2025 and separately for each neighbourhood. This analysis is processed for better understanding of crime volume trends in Toronto over time in the past and in the future, so connected  departments of police forces could make desisions based on this data in their processes and implement required changes.

# Methodology

## Steps taken:

1. Data Cleaning: Handling missing values, removing inconsistencies, and ensuring data readiness.
2. Preliminary analysis to identify correlation: Understanding patterns, correlations, and data distribution.
3. Forcasting model: applying ARIMA model to determine crime volume in Toronto in 2025 in total and per each neighbourhood. Additionally, creating training and test sets and assessing model accuracy.
4. Visualization: Creating plots using python and Tableau to represent insights and model results.
5. Conclusion.

## Technical Stack:

### Programming Language:

Python

### Libraries Used:

Numpy: matrix operations
Pandas: data analysis
Matplotlib: creating graphs and plots
Plotly: creating graphs and plots
Seaborn: enhancing matplotlib plots
Pmdarima: ARIMA model for predicting analysis


### Other tools:

Tableau

# Project Scope

The analysis includes:
- defining crime volume trend over time in top 3 neighbourhoods;
- reviling top 10 neighbourhoods with high volume of crimes in total through 11 years;
- predicting crime volume trend in 2025 in total;
- forcasting crime volume trend in 2025 for each neighbourhood.

## Description

## Stakeholders

### Government and Law Enforcement:
- **Toronto Police Service** - directing patrol resources, justifying budget requests for specific units (e.g., gun violence or organized crime), planning targeted intervention programs, and setting operational priorities for the year.
- **Toronto City Council** - evaluating the success of current public safety initiatives, allocating the city budget, informing policy debates (e.g., transit security, mental health response), and addressing public concern.
- **Public Transit Agencies** - identifying high-crime subway stations or bus routes to justify increased security presence (special constables, security guards, CCTV deployment).
- **Provincial/Federal Government** - supporting applications for federal/provincial funding for specific crime reduction programs in targeted areas of the city.

### Business and Finance:
- **Real Estate Developers/Investors** - determining the desirability, safety, and future value of areas for new residential or commercial developments.
- **Insurance Companies** - calculating premiums for property, business, and auto insurance based on the forecasted crime rates and types in specific Toronto neighbourhoods.
- **Local Businesses** - justifying investment in local security patrols, retail loss prevention, and enhanced surveillance systems for the coming year.
- **Tourism Sector** - monitoring trends, especially in downtown areas, to assess and manage public messaging regarding the safety of visitors.

### Community and Advocacy Groups:
- **Neighbourhood/Community Associations** - using data to lobby City Council and the Police for more resources, organize community safety meetings.
- **Schools, Universities, and Hospitals** - assessing safety risks near their locations and adjusting security protocols (e.g., lighting, campus police patrols) for the upcoming year.
- **Social Service/Non-Profit Organizations** - directing resources (e.g., youth outreach, mental health support) to high-risk areas identified by the detailed crime type and area data.
- **General Public/Residents** - deciding where to live, focusing on personal security measures, and engaging in local political debates regarding safety.


# Data Cleaning

After reviewing the dataset for common data quality issues — such as missing values, duplicate records, and inconsistent formatting — several adjustments were made. 
1. I have identified that some column titles consist of name of the crime and year, which is difficult to use for the analysis. I got the list of the unique titles and splitted them into "Crime Type" and "Year" columns using .melt, .split and lambda + pd.Series Python tools. 
2. I have also excluded "POPULATION" rows from "Crime Type".
3. The null values vere filled with numberic "0" value using .fillna in order to have all numberic values in the same type of data.
4. I have checked if dataset includes null values and the amount of such values using .notna method.
5. In the end, cleened dataframe was grouped by "Crime Type" and "Year".

#### Tools used:
- .describe
- .tolist
- .melt
- .fillna
- .split
- .apply
- lambda
- .Series
- .unique
- .rename
- .groupby
- .notna

Results:
 - No missing values in the dataset;
 - No whitespaces or random symbols in both numeric and categorical columns;
 - Summary statistics for all columns:
 ![Summary statistics for all columns](/img/)

 Summary statistics for numerical features:
   
 ![Summary statistics for numerical features](/img/)

# Analysis

### Why I Chose to Use a Machine Learning Model:
In this project I aim to identify the trends of crime volume for the neighbourhoods in Toronto over time period of 2014 to 2024 and possibility of prediction of the crime trend for the following year - 2025. The simple data analysis and visualizations can reviel the surface of the trends for the crimes in different neighbourhoods over time, however I chose ARIMA model to forecast the trend for 2025 year to strengthen the analysis and insights.

## Model description

ARIMA model combines both Autoregressive and Moving Average modelings in it, which is beneficial for time series forecasting. In this case I predict the future simply based on patterns in the past data (2014 - 2024 years). 

## Predictive Power and Interpretability:

ARIMA models are a powerful tool for analyzing time series data to understand past processes as well as for forecasting future values of a time series. I have used Auto-ARIMA model, which applies automated configuration tasks to generating and comparing ARIMA models. The algorithm generates multiple models and attempts to minimize the AICc and the error of the Maximum Likelihood Estimation to obtain the best ARIMA model.

## Analysis Value:

The outcome of the analysis and prediction can be valuable in multiple areas and for various groups of society. The analysis of crime trends in neighbourhoods can be insightful for government, businesses and the communities located in the corresponding areas:
- **Government** can focus on evaluating the success of current public safety initiatives, planning police budgets and developing projects for providing safety to the citizens.
- **Business** can predict the safest areas for evolving by oparating the results of the analysis.
- **Comunities** can plan their lives and organize safety with the help of non-profit organizations.

## Model Performance Summary:



## Prediction Results:

# Visualization

# Conclusion

# Credits and Source
