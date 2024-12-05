## Important Points of Boston House Price Prediction 
**CHAS column**<br>
In statistical modeling or data analysis, a dummy variable (also known as an indicator variable) is used to represent categorical data with binary values (0 or 1). It is commonly used in regression models to assess the effect of categorical factors on a dependent variable.<br>
data.CHAS is a dummy variable, where 1: The tract or area borders the Charles River (i.e., it is near or on the riverbank). 0: The tract or area does not border the Charles River.<br><br>
**Import Statements**<br>
<code>from sklearn.model_selection import train_test_split</code><br>
<code>from sklearn.linear_model import LinearRegression</code><br><br>
**Code Explaination**<br>
<code>target=data['PRICE']
 features=data.drop('PRICE',axis=1)
 X_train, X_test, y_train, y_test = train_test_split(features, target, test_size=0.2,random_state=10)</code><br>
 <br>*test_size=0.2:* This parameter specifies the proportion of the dataset to include in the test split. The value 0.2 means that 20% of the data will be used for testing, and the remaining 80% will be used 
 for training the model.<br>
 *random_state=10:* This is a seed for the random number generator, ensuring that the split is reproducible. When you specify a random state, it guarantees that every time you run the code with that same random state, you'll get the same split. This is important for consistency when developing and testing machine learning models.<br><br>
X_train: This is the subset of the features that will be used to train the machine learning model. It contains 80% of the original feature data.<br>
X_test: This is the subset of the features that will be used to test the machine learning model. It contains 20% of the original feature data.<br>
y_train: This is the subset of the target variable (housing prices) that will be used to train the model. It contains the target values corresponding to the training data (X_train).<br>
y_test: This is the subset of the target variable that will be used to test the model. It contains the target values corresponding to the test data (X_test).<br>

**fit():**<br> This method is used to train the linear regression model. It takes in the training data and fits the model to the data.
<br>
**R-Squared**<br>
score(): This method calculates the R-squared (R²) value, which is a measure of how well the model explains the variance in the target variable (y_train).<br>
•	R² measures the proportion of the variance in the dependent variable (y) that is predictable from the independent variables (X).<br>
•	R² = 1: This indicates a perfect fit — the model explains 100% of the variance in the data.<br>
•	R² = 0: This indicates that the model explains none of the variance, meaning the model is no better than simply predicting the mean value of the target variable.<br>
•	Negative R²: This can occur if the model performs worse than a simple mean-based model.<br><br>

**LOG**<br>
Taking the logarithm of prices is used when prices exhibit skewness as in our case.The log transformation helps in making the distribution more symmetric and often reduces the influence of outliers.<br>

**Important** In our case the regression model by simple linear regression was not much suitable, so we have used log values of prices which compartively provided better results. 
