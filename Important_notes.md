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
