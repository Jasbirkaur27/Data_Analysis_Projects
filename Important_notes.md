### How to add image in jupyter notebook
**Adding image using link**<br>
<code>from IPython.display import Image
Image(url='https://i.imgur.com/aKcwkSx.png')</code>
<br>
<br>

**Adding image using file path**<br>
1.The first step is to import the libraries that we need to display images in Jupyter Notebook. We will be using the Pillow library to read the image and the IPython.display library to display the image.<br>
2.The next step is to load the image that we want to display. We will use the Image.open() method from the Pillow library to load the image.<br>
3.We can display the image using the display() method from the IPython.display library.<br>
 Example Code:<br>
  <code>from PIL import Image
  from IPython.display import display
  img = Image.open('./assets/bricks.jpg')
  display(img)</code><br>
  This will display the image.
<br>
### Resampling Time Series Data <br>
To convert our daily data into monthly data, we're going to use the .resample() function. The only things we need to specify is which column to use (i.e., our DATE column) and what kind of sample frequency we want (i.e., the "rule"). We want a monthly frequency, so we use 'M'.<br>
After resampling, we need to figure out how the data should be treated. In our case, we want the last available price of the month - the price at month-end.<br>
1.	<code>df_btc_monthly = df_btc_price.resample('M', on='DATE').last()</code><br>
If we wanted the average price over the course of the month, we could use something like:<br>
2.<code>df_btc_monthly = df_btc_price.resample('M', on='DATE').mean()</code><br>
### Rolling Average
A rolling average, sometimes referred to as a moving average, is a metric that calculates trends over short periods of time using a set of data.For instance, if your data set includes many points where the numbers shift up and down drastically, you might not see whether it trends up or down over time.To discover the trend, a rolling average uses smaller parts of the data. For instance, you might use the numbers collected over the last 30 days and find out their average. Then, the average rolls or moves for each new period. Making these calculations for every 30 day period allows professionals to discover the way the average changes as time moves forward.
<br>
<code>roll_df = df_unemployment[['UE_BENEFITS_WEB_SEARCH', 'UNRATE']].rolling(window=6).mean()</code>
<br>
### Box Plot
Boxplots, also known as **box-and-whisker plots**, are a standard way of displaying data distribution based on a five-number summary: minimum, first quartile (Q1), median, third quartile (Q3), and maximum.Boxplots are particularly useful for identifying outliers and understanding the spread and skewness of the data. They are also used when comparing multiple groups or visualizing the distribution of a single variable.<br>
### Pearson Correlation:
The pearson function from scipy.stats calculates the Pearson correlation coefficient, which measures the strength and direction of the linear relationship between two variables. In Rainfall analysis , it is used to assess how well each seasonal rainfall period (e.g., Jan-Feb) correlates with the annual rainfall.
The Pearson correlation values you provided for the seasonal rainfall periods indicate the strength and direction of the linear relationship between the seasonal rainfall and the total annual rainfall ('ANNUAL').<br>
**Example:** Correlation: 0.930 (very strong positive)<br>
The correlation between rainfall in June-September and the total annual rainfall is very strong. This means that the total amount of rainfall in these months (likely corresponding to the monsoon or rainy season) is a very good predictor of the overall annual rainfall. Years with high rainfall in the Jun-Sep period tend to have high total annual rainfall, while years with low rainfall in this period tend to have low annual totals. This could indicate that the bulk of the annual rainfall is concentrated in this season, making it the key determinant of total rainfall for the year.
<br>
### Anomaly Detection
An outlier is a data point that differs significantly from other data points in the given dataset.Anomaly detection is the process of finding the outliers in the data, i.e. points that are significantly different from the majority of the other data points.

### Isolation Forest algorithm
 It’s an unsupervised learning algorithm that identifies anomaly by isolating outliers in the data.Isolation Forest is based on the Decision Tree algorithm. It isolates the outliers by randomly selecting a feature from the given set of features and then randomly selecting a split value between the max and min values of that feature. This random partitioning of features will produce shorter paths in trees for the anomalous data points, thus distinguishing them from the rest of the data.
<br><code>from sklearn.ensemble import IsolationForest</code><br>
### Prophet Library
Prophet is a forecasting library designed to handle time series data with daily observations that may contain missing data and outliers. It is widely used  for predicting future trends based on historical data. Prophet is particularly well-suited for time series that exhibit seasonal effects (e.g., yearly, weekly) and trends that may change over time.<br>
**Prophet is mainly used for**:<br>
Demand forecasting: Predicting the demand for products or services in future periods.<br>
Sales forecasting: Estimating future sales based on historical data.<br>
Financial forecasting: Predicting stock prices or market trends.<br>
Environmental data analysis: Forecasting weather conditions, temperature, or rainfall (as shown in your example).<br>
Supply chain management: Estimating future supply and demand in operations.<br>
<br>
### perasonr
pearsonr: This function from scipy.stats is used to compute the Pearson correlation coefficient between two datasets. It returns two values: the correlation coefficient and the p-value (a measure of statistical significance).<br>
Pearson Correlation Coefficient (r):<br>

Measures the linear correlation between two variables.<br>
**The value of r ranges from -1 to 1**<br>
1: Perfect positive correlation (as one variable increases, the other increases).<br>
-1: Perfect negative correlation (as one variable increases, the other decreases).<br>
0: No correlation (the variables do not have a linear relationship).<br>
<br>
**Interpretation of Pearson's Correlation:**<br>
r > 0.8: Strong positive correlation.<br>
r > 0.5: Moderate positive correlation.<br>
r > 0 but < 0.5: Weak positive correlation.<br>
r < 0 but > -0.5: Weak negative correlation.<br>
r < -0.5: Moderate negative correlation.<br>
r < -0.8: Strong negative correlation.<br>
**p-value:** The pearsonr function also returns a p-value, which helps determine if the correlation is statistically significant. A small p-value (typically < 0.05) indicates strong evidence against the null hypothesis (no correlation).<br>
<br> 
### Lagged Effects Analysis
Lagging is used in time series analysis to see if changes in a variable (like CO₂) affect another variable (like temperature) with a delay. This can be useful when you suspect that the effects of CO₂ concentration are not immediate but rather have a delayed impact on temperature change.<br>
After creating these lagged variables, we will fit an Ordinary Least Squares (OLS) regression model. This model will use current and lagged CO₂ levels as predictors to estimate their contribution to current temperature anomalies.<br>
With refrence to carbon emmision dataset, <br>
we will determine:<br>
1.	How strongly current CO₂ levels affect temperature changes.<br>
2.	Whether CO₂ levels from previous years have a significant impact.<br>

**Ordinary Least Squares (OLS) Regression**
OLS is a statistical method used to estimate the relationship between one dependent variable and one or more independent variables. The goal is to minimize the difference between observed values and predicted values.<br>
OLS is used when we want to understand or predict the linear relationship between variables. It's suitable when the relationship is continuous and linear, and the residuals (errors) are normally distributed.<br>
**Important Assumptions:** <br>
Linearity: The relationship between the dependent and independent variables should be linear.<br>
Homoscedasticity: The variance of residuals should be constant across all levels of the independent variables.<br>
Independence: Observations should be independent of each other.<br>
Normality of residuals: The residuals (errors) should be normally distributed.<br>
<br>
Investigating the effect of past CO₂ levels on future temperature change.<br>
Predicting future events or conditions based on historical data.<br><br>
**Model Evaluation** <br>
After fitting a regression model, it's crucial to evaluate its performance using metrics like R-squared, p-values, and coefficients.Evaluate your model to ensure it explains the data adequately and that the coefficients are statistically significant. If necessary, you can refine the model by adding/removing variables or adjusting for non-linearity.<br><br>

**When to Use These Techniques**<br>
•	Time Series Forecasting: When you are working with time-dependent data and want to predict future values (e.g., predicting temperature change based on historical CO₂ levels).<br>
•	Understanding Relationships Over Time: When you need to understand how past events (lagged variables) influence current conditions. For example, how past CO₂ levels might be linked to future temperature changes.<br>
•	Policy and Impact Analysis: In fields like climate science or economics, understanding the impact of past variables on future conditions is important for decision-making and policy.<br>
<br>
## Getting real time data from API
<code>import pandas as pd
import yfinance as yf
from datetime import date, timedelta
end_date = date.today().strftime("%Y-%m-%d")
start_date = (date.today() - timedelta(days=365)).strftime("%Y-%m-%d")
tickers = ['RELIANCE.NS', 'TCS.NS', 'INFY.NS', 'HDFCBANK.NS']
data = yf.download(tickers, start=start_date, end=end_date, progress=False)
data = data.reset_index()
data_melted = data.melt(id_vars=['Date'], var_name=['Attribute', 'Ticker'])
data_pivoted = data_melted.pivot_table(index=['Date', 'Ticker'], columns='Attribute', values='value', aggfunc='first')
stock_data = data_pivoted.reset_index()
print(stock_data.head())</code><br>
**Explaination** :<br>
- yfinance as yf: This imports the yfinance library as yf, which allows for fetching financial data from Yahoo Finance.<br>
- from datetime import date, timedelta: This imports the date and timedelta classes from Python's datetime module. date represents a date object, and timedelta represents a difference between two dates.<br>
- The .NS suffix indicates that these are Indian stocks listed on the National Stock Exchange of India (NSE).<br>
- <code>data_melted = data.melt(id_vars=['Date'], var_name=['Attribute', 'Ticker'])</code><br>
The melt() function is used to reshape the DataFrame from wide format (multiple columns for each stock attribute) into long format (one column for each attribute and ticker).<br>
The id_vars=['Date'] means that the Date column will remain as is, and the other columns will be melted into two new columns: Attribute and Ticker.<br>
The column names like RELIANCE.NS Open, TCS.NS Close, etc., will be split into Attribute and Ticker based on the stock and the attribute.<br>
The resulting data_melted DataFrame will have three columns: Date, Attribute, and Ticker, along with a value column that stores the respective stock data.<br>
 
