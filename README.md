# Timse-Series-Analysis
A time series analysis models and descriptions

## DATA:
The term "univariate time series" refers to a time series that consists of single (scalar) observations recorded sequentially over equal time increments. Some examples are [monthly CO2 concentrations](https://itl.nist.gov/div898/handbook/pmc/section4/pmc4411.htm) and [southern oscillations to predict el nino effects](https://itl.nist.gov/div898/handbook/pmc/section4/pmc4412.htm).
Although a univariate time series data set is usually given as a single column of numbers, time is in fact an implicit variable in the time series. If the data are equi-spaced, the time variable, or index, does not need to be explicitly given. The time variable may sometimes be explicitly used for plotting the series. However, it is not used in the time series model itself.

The analysis of time series where the data are not collected in equal time increments is beyond the scope of this handbook. 

| CO2 | YearMonth | Year | Month |
| :--- | :--- | :--- | :--- |
| 330.62 | 1975.04 | 1975 | 1 |
| 331.40 | 1975.13 | 1975 | 2 |
| 331.87 | 1975.21 | 1975 | 3 |
| 333.18 | 1975.29 | 1975 | 4 |
| 333.92 | 1975.38 | 1975 | 5 |
| 333.43 | 1975.46 | 1975 | 6 |
| 331.85 | 1975.54 | 1975 | 7 |
| 330.01 | 1975.63 | 1975 | 8 |
| 328.51 | 1975.71 | 1975 | 9 |
| 328.41 | 1975.79 | 1975 | 10 |
| 329.25 | 1975.88 | 1975 | 11 |
| 330.97 | 1975.96 | 1975 | 12 |

## Important Concepts
🎓 Trends
Trends are defined as measurable increases and decreases over time. Read more. In the context of time series, it's about how to use and, if necessary, remove trends from your time series.

🎓 Seasonality
Seasonality is defined as periodic fluctuations, such as holiday rushes that might affect sales, for example. Take a look at how different types of plots display seasonality in data.

🎓 Outliers
Outliers are far away from the standard data variance.

🎓 Long-run cycle
Independent of seasonality, data might display a long-run cycle such as an economic down-turn that lasts longer than a year.

🎓 Constant variance
Over time, some data display constant fluctuations, such as energy usage per day and night.

🎓 Abrupt changes
The data might display an abrupt change that might need further analysis. The abrupt shuttering of businesses due to COVID, for example, caused changes in data.

________________________________________________________________________________________________________________________
🎓 Stationarity
From a statistical context, stationarity refers to data whose distribution does not change when shifted in time. Non-stationary data, then, shows fluctuations due to trends that must be transformed to be analyzed. Seasonality, for example, can introduce fluctuations in data and can be eliminated by a process of 'seasonal-differencing'.

🎓 Differencing
Differencing data, again from a statistical context, refers to the process of transforming non-stationary data to make it stationary by removing its non-constant trend. "Differencing removes the changes in the level of a time series, eliminating trend and seasonality and consequently stabilizing the mean of the time series."
________________________________________________________________________________________________________________________