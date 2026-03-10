## Autoregressive Integrated Moving Average

In time series analysis used in statistics and econometrics, autoregressive integrated moving average (ARIMA) and seasonal ARIMA (SARIMA) models are generalizations of the autoregressive moving average (ARMA) model to non-stationary series and periodic variation, respectively. All these models are fitted to time series in order to better understand it and predict future values. The purpose of these generalizations is to fit the data as well as possible. Specifically, ARMA assumes that the series is stationary, that is, its expected value is constant in time. If instead the series has a trend (but a constant variance/autocovariance), the trend is removed by "differencing",[1] leaving a stationary series. This operation generalizes ARMA and corresponds to the "integrated" part of ARIMA. Analogously, periodic variation is removed by "seasonal differencing". [wiki](https://en.wikipedia.org/wiki/Autoregressive_integrated_moving_average)

#### Note

Before working with ARIMA models, two critical concepts stand out in order to understand the nature of the data:
Stationarity: This refers to the property where the statistical characteristics of the data (such as mean and variance) do not change over time. If the data contains a trend or seasonality, it is considered non-stationary and must be transformed before applying an ARIMA model.
Differencing: This is the process of subtracting each data point from the previous one to make non-stationary data stationary. By doing so, it removes trend and seasonality and stabilizes the mean.

## General Concepts

🎓AR - for AutoRegressive:
Autoregressive models, as the name implies, look 'back' in time to analyze previous values in your data and make assumptions about them. These previous values are called 'lags'. An example would be data that shows monthly sales of pencils. Each month's sales total would be considered an 'evolving variable' in the dataset. This model is built as the "evolving variable of interest is regressed on its own lagged (i.e., prior) values."

🎓I - for Integrated:
As opposed to the similar 'ARMA' models, the 'I' in ARIMA refers to its integrated aspect. The data is 'integrated' when differencing steps are applied so as to eliminate non-stationarity.

🎓MA - for Moving Average:
An MA model expresses the current value of a time series as a linear function of current and past random shocks (error terms) with finite lag length. In contrast to an autoregressive model, which regresses the variable on its past values, the moving-average model relies solely on the dependency structure of the error terms.[wiki](https://en.wikipedia.org/wiki/Moving-average_model)

#### 🛠️ **Implementation Steps: Electricity Consumption Forecasting**

The document builds a model step by step using electricity load data:

**1. Data Preparation and Scaling**

**Time Period:** The data is divided into training (November–December 2014) and test sets. It is critical that the test set is from a later date than the training set in order to prevent “future data leakage.”

**MinMaxScaler:** The data is scaled between 0 and 1. This helps the model converge faster and more stably.
<p>
$$
X_{\text{scaled}} = \frac{X - X_{\min}}{X_{\max} - X_{\min}}
$$
</p>

**2. Building the SARIMAX Model**

Since electricity data is seasonal (day/night cycle), **SARIMAX** is used. The model is defined with the following parameters:

**Trend Parameters (p, d, q):** Past values, degree of differencing, and error terms.

**Seasonal Parameters (P, D, Q, s):** The same components within the seasonal cycle (for example, a 24-hour period).


ARIMAX, standart ARIMA modeline Dışsal Değişkenlerin (Exogenous variables) eklenmiş halidir. Yani sadece geçmiş satışlara bakmaz, örneğin "o gün hava durumu nasıldı?" veya "indirim var mıydı?" gibi dış faktörleri de denkleme dahil eder.

Matematiksel olarak şu parçalardan oluşur:
<p align="center">

$$
Y_t = \nu + \sum_{i=1}^{p} \phi_i Y_{t-i} + \sum_{j=1}^{q} \theta_j \epsilon_{t-j} + \sum_{k=1}^{r} \beta_k X_{k,t} + \epsilon_t
$$

</p>
Where:

- $Y_t$ : The value we are trying to predict (Ex: Electricity consumption at time $t$)
- $\nu$ : Intercept term (Constant Value)
- $\phi_i$ : Autoregressive coefficients (Effect of past values on todays value)
- $\theta_j$ : Moving average coefficients
- $\beta_k$ : Coefficients for exogenous variables
- $X_{k,t}$ : Exogenous variables at time $t$
- $\epsilon_t$ : Error term