## Portfolio Optimization: Case Study
The dataset consists of historical stock market data for multiple companies, including columns such as Date, Ticker, Adjusted Close, Close, High, Low, Open, and Volume. The data spans a significant period, providing daily price and volume information for each stock.<br>
Stock market portfolio optimization is the process of selecting the best combination of stocks to maximize returns while minimizing the risk, based on historical performance data and financial metrics.<br>
### Problem
The goal is to develop a portfolio optimization strategy using the given stock market data. This involves analyzing historical price trends, calculating key financial metrics, and applying Modern Portfolio Theory (MPT) to construct an efficient portfolio. The primary objectives are:<br>
- Identify trends in stock prices using moving averages and other technical indicators.<br>
- Calculate the volatility and risk associated with each stock.<br>
- Determine the correlation between different stocks to understand their relationships and potential diversification benefits.<br>
- Generate and evaluate a series of random portfolios to identify the optimal portfolio that maximizes the Sharpe ratio, balancing risk and return effectively.<br>**Expected results include:**
- Identification of the portfolio with the maximum Sharpe ratio, including the weights of each stock and the associated risk-return profile.<br>
- Recommendations for constructing a diversified investment portfolio that maximizes returns while minimizing risk, based on the historical performance and statistical analysis of the provided stock data.<br>
## Data
I have collected real-time stock market data using the yfinance API.If you are using this library for first time you need to install it.The code for installing <br>
<code>pip install yfinance</code>
I have collected data of four companies  RELIANCE, TCS, INFY, HDFCBANK.
## Major issue 
- In stock market analysis, the Adjusted Close (Adj Close) price is commonly used as it accounts for critical corporate actions, such as dividends and stock splits. These adjustments provide a more accurate reflection of an investor's actual returns over time. Traditionally, the yfinance library has included the Adj Close column by default when downloading stock data. However, due to recent updates, yfinance no longer includes this column by default.<br>
- To retrieve more comprehensive data, including dividends and stock splits, the actions=True argument must be specified when downloading data using yfinance. Unfortunately, despite setting actions=True, the dividends and stock splits values for the selected stocks returned as 0.0.<br>
- Given this limitation, I proceeded with the analysis using the Close prices instead. While Close prices do not account for dividends or stock splits, they still provide useful insights for portfolio optimization and risk-return analysis, allowing us to explore the performance of the stocks over the selected period.<br>
### Key Points of Analysis 
**Mean Returns**<br>
tock prices usually change by a small fraction on a daily basis, and daily returns are expressed as a percentage (or decimal). For example, a return of 0.000417 is equivalent to 0.0417% for that day. When compounded over a year, these mean returns can result in significant cumulative annual returns.<br>
**Variance of each stock** <br>
HDFCBANK.NS (0.000199), INFY.NS (0.000205), RELIANCE.NS (0.000209),  TCS.NS (0.000176) <br>
A higher variance indicates higher volatility, meaning the stock price fluctuates more widely. In this case, RELIANCE.NS has the highest variance, suggesting that it has the most volatility, while TCS.NS has the lowest variance, suggesting it is the least volatile.<br>
**CLosing Prices** <br>
- The graph of HDFC Bank's closing prices exhibits a clear upward trend, albeit with some fluctuations. These variations indicate periodic adjustments, but the overall trajectory remains positive.<br>
- The closing prices of (INFY) demonstrate significant volatility. Initially, the price experienced an increase, followed by a steady decline for several months. However, in the middle of the year, the prices began to rebound, signaling a recovery and renewed growth.<br>
- Reliance Industries' closing price remained relatively stable around ₹1400 for a considerable period, but over the course of a quarter, it exhibited a consistent downward movement, reflecting a period of negative performance.<br>
- For Tata Consultancy Services (TCS), the first half of the year saw the closing prices fluctuating around ₹3800. However, in the latter half, the stock experienced a notable upward movement, with prices increasing by an average of ₹400, indicating a strong rally in the second half of the year.<br>

