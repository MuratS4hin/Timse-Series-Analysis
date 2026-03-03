## Autoregressive Integrated Moving Average

In time series analysis used in statistics and econometrics, autoregressive integrated moving average (ARIMA) and seasonal ARIMA (SARIMA) models are generalizations of the autoregressive moving average (ARMA) model to non-stationary series and periodic variation, respectively. All these models are fitted to time series in order to better understand it and predict future values. The purpose of these generalizations is to fit the data as well as possible. Specifically, ARMA assumes that the series is stationary, that is, its expected value is constant in time. If instead the series has a trend (but a constant variance/autocovariance), the trend is removed by "differencing",[1] leaving a stationary series. This operation generalizes ARMA and corresponds to the "integrated" part of ARIMA. Analogously, periodic variation is removed by "seasonal differencing". [wiki](https://en.wikipedia.org/wiki/Autoregressive_integrated_moving_average)

## General Concepts

🎓AR - for AutoRegressive:
Autoregressive models, as the name implies, look 'back' in time to analyze previous values in your data and make assumptions about them. These previous values are called 'lags'. An example would be data that shows monthly sales of pencils. Each month's sales total would be considered an 'evolving variable' in the dataset. This model is built as the "evolving variable of interest is regressed on its own lagged (i.e., prior) values."

🎓I - for Integrated:
As opposed to the similar 'ARMA' models, the 'I' in ARIMA refers to its integrated aspect. The data is 'integrated' when differencing steps are applied so as to eliminate non-stationarity.

🎓MA - for Moving Average:
An MA model expresses the current value of a time series as a linear function of current and past random shocks (error terms) with finite lag length. In contrast to an autoregressive model, which regresses the variable on its past values, the moving-average model relies solely on the dependency structure of the error terms.[wiki](https://en.wikipedia.org/wiki/Moving-average_model)