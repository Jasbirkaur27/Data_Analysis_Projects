# Machine Learning
### Introduction 
Machine Learning means using data and algorithms to build intelligent systems. Machine Learning algorithms are computational procedures that enable machines to learn patterns and relationships from data without being explicitly programmed. These algorithms allow machines to make predictions, decisions, and classifications based on the patterns they have learned from the data. <br>
Various Types of Machine Learning Algorithms:<br>
1.Regression Algorithms<br>
2.linear Classification Algorithms<br>
3.Naive Bayes Algorithms<br>
4.SVM And KNN Algorithms<br>
5.Decision Tree<br>
6.CLusturing Algorithms <br>
In Python we  use the scikit-learn library , which provides the functionality of implementing all Machine Learning algorithms.<br><br>
## Regession 
Regression is a statistical method for modeling the relationship between a dependent variable (target) and one or more independent variables (predictors). The goal of regression is to understand how changes in one predictor affect the target variable.<br>
### Linear Reagression Algorithm 
 It finds the best-fit line that describes the relationship between the input variable and the output variable so we can predict the output variable based on a new input variable.<br>
**Implementation**<br>
<code>from sklearn.linear_model import LinearRegression
model = LinearRegression().fit(x, y)</code>
We can predict the value of any new data using this model.A random example of how this can be done is:
<code>new_money_made = model.predict(new_num_cupcakes)</code>
<br><br>
### Polynomial Regression
Polynomial regression is an algorithm that allows us to model nonlinear relationships between input features and output labels. It can be used in real-time business problems, such as sales forecasting, where the relationship between variables is not linear.It is used when using a straight line is not possible to find relationship between two variables,it helps to create a polynomial curve of degree'n' to the data points.<br>
**Steps to Implement Polynomial Regression:** <br>
Transform Data: we use PolynomialFeatures from sklearn.preprocessing to transform the features into polynomial terms.<br>
Train the Model:we use the transformed features to train a linear regression model.<br>
Make Predictions:we use the trained model to make predictions.<br>
Visualize the Results: Plot both the original data and the polynomial regression curve.<br>
Use metrics such as Mean Squared Error (MSE) or R-squared to evaluate the performance of the polynomial regression model.<br>
**Degree of polynomial** <br>
Choosing the right degree of polynomial is a balance between underfitting and overfitting.We can determine the degree by visualizating our data.<br>
If possible,we plot our data points to see if the relationship appears linear or curved. If the data appears to follow a simple curve (e.g., quadratic or cubic), starting with a lower degree might work well.<br>
Model Comparison: Start with low-degree polynomials and gradually increase the degree. Visualize the fit of the model on the data to observe whether the fit improves or becomes unnecessarily complex.<br>
### Ridge and Lasso Regression
Ridge and Lasso Regression are regularization techniques used in linear regression to prevent overfitting and improve the model’s generalization to unseen data. They work by adding a penalty term to the linear regression loss function. They work by adding a penalty term to the linear regression loss function.<br><br>
**Ridge Regression**<br>
Ridge Regression, also known as L2 regularization, adds a penalty term proportional to the square of the magnitude of the coefficients. It encourages the model to have smaller but non-zero coefficients. It helps in reducing the impact of high-value coefficients and, in turn, the risk of overfitting.Ridge Regression works by introducing a penalty term. This penalty term restricts the magnitude of the coefficient estimates, thereby reducing their sensitivity to small changes in the input data. By adding this penalty, Ridge Regression shrinks the coefficients towards zero, but they do not become exactly zero. It allows the algorithm to handle multicollinearity and provide more stable and reliable predictions.<br>
<br>
**Lasso Regression**, also known as L1 regularization, adds a penalty term proportional to the absolute values of the coefficients. It is a type of regression algorithm used for feature selection and regularization. It is similar to ridge regression, but it adds an L1 penalty term to the regression equation, resulting in a sparse model where some of the coefficients are set to zero.<br>
<br>
## Random Forest Aglorithm
Random Forests are known for their ability to handle high-dimensional data, handle missing values, and perform feature selection. It combines the opinions of many “experts”, called decision trees. Each decision tree looks at a subset of data and predicts based on predefined rules. When you have many decision trees, you can predict by taking the average of their predictions. It helps reduce the impact of an individual tree making a mistake.<br><br>
Random Forest algorithm is an ensemble learning method for classification and regression tasks. It is composed of multiple decision trees, where each tree is built on a random subset of the input features and a random subset of the training data. During the learning phase, each decision tree is built by recursively partitioning the data into subsets based on the values of the input features. Split points are chosen to maximize information gain or decrease impurity in each node. The final result of the algorithm is obtained by aggregating the predictions of all the trees, typically taking a majority vote for classification problems or the average for regression problems.<br><br>
