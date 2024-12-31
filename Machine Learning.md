# Machine Learning
### Introduction 
Machine Learning means using data and algorithms to build intelligent systems. Machine Learning algorithms are computational procedures that enable machines to learn patterns and relationships from data without being explicitly programmed. These algorithms allow machines to make predictions, decisions, and classifications based on the patterns they have learned from the data. <br><br>
Various Types of Machine Learning Algorithms:<br>
1.Regression Algorithms<br>
2.linear Classification Algorithms<br>
3.Naive Bayes Algorithms<br>
4.SVM And KNN Algorithms<br>
5.Decision Tree<br>
6.CLusturing Algorithms <br>
In Python we  use the scikit-learn library , which provides the functionality of implementing all Machine Learning algorithms.<br>
## Regession 
Regression is a statistical method for modeling the relationship between a dependent variable (target) and one or more independent variables (predictors). The goal of regression is to understand how changes in one predictor affect the target variable.<br>
### Linear Reagression Algorithm 
 It finds the best-fit line that describes the relationship between the input variable and the output variable so we can predict the output variable based on a new input variable.<br>
**Implementation**<br>
<code>from sklearn.linear_model import LinearRegression
model = LinearRegression().fit(x, y)</code><br>
We can predict the value of any new data using this model.A random example of how this can be done is:<br>
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
Ridge and Lasso Regression are regularization techniques used in linear regression to prevent overfitting and improve the model’s generalization to unseen data. They work by adding a penalty term to the linear regression loss function. They work by adding a penalty term to the linear regression loss function.<br>
**Ridge Regression**<br>
Ridge Regression, also known as L2 regularization, adds a penalty term proportional to the square of the magnitude of the coefficients. It encourages the model to have smaller but non-zero coefficients. It helps in reducing the impact of high-value coefficients and, in turn, the risk of overfitting.Ridge Regression works by introducing a penalty term. This penalty term restricts the magnitude of the coefficient estimates, thereby reducing their sensitivity to small changes in the input data. By adding this penalty, Ridge Regression shrinks the coefficients towards zero, but they do not become exactly zero. It allows the algorithm to handle multicollinearity and provide more stable and reliable predictions.<br>
**Lasso Regression**, also known as L1 regularization, adds a penalty term proportional to the absolute values of the coefficients. It is a type of regression algorithm used for feature selection and regularization. It is similar to ridge regression, but it adds an L1 penalty term to the regression equation, resulting in a sparse model where some of the coefficients are set to zero.<br>

### Random Forest Aglorithm
Random Forests are known for their ability to handle high-dimensional data, handle missing values, and perform feature selection. It combines the opinions of many “experts”, called decision trees. Each decision tree looks at a subset of data and predicts based on predefined rules. When you have many decision trees, you can predict by taking the average of their predictions. It helps reduce the impact of an individual tree making a mistake.<br>
Random Forest algorithm is an ensemble learning method for classification and regression tasks. It is composed of multiple decision trees, where each tree is built on a random subset of the input features and a random subset of the training data. During the learning phase, each decision tree is built by recursively partitioning the data into subsets based on the values of the input features. Split points are chosen to maximize information gain or decrease impurity in each node. The final result of the algorithm is obtained by aggregating the predictions of all the trees, typically taking a majority vote for classification problems or the average for regression problems.<br><br>
**Real Life Example** : As the third umpire in cricket checks from different angles to give final results. Random Forest uses row sampling and random feature selection for individual trees to get a different view of the data. <br><br>
### Logistic Regression 
Logistic Regression is a statistical model used for binary classification problems. It is used to predict the probability of an outcome based on the input features. It uses a sigmoid function to map the input features to output the probability.The core idea behind logistic regression is to find the best-fitting model that predicts the probability of a particular class, based on one or more independent variables (features).<br>
**Example**: Let's consider a real-world example where we want to predict whether a customer will buy a product based on some factors.<br>
--The logistic regression algorithm uses the data to find the relationship between the input features (age, income, and purchase history) and the probability of a customer buying the product.<br>
--The model will learn to assign weights (coefficients) to each feature based on how important each one is for predicting the purchase behavior.<br>
--Once the model is trained, it can predict the probability that a new customer will buy the product. For example, if a new customer is 30 years old, has an income of $50,000, and has previously bought a product, the model will calculate the probability that this customer will buy the product again.<br>
**Interpretation**:If the model predicts a probability greater than 0.5, the model will classify this customer as likely to buy the product (class = 1). If the probability is less than 0.5, the model will classify the customer as unlikely to buy (class = 0).<br>
<br>
Logistic regression is a foundational algorithm in machine learning, especially useful for binary classification tasks. Its probabilistic nature makes it interpretable and suitable for problems like predicting customer behavior, determining the likelihood of a disease, spam email detection, and many other applications.<br>
IMPORTANT :It can be sensitive to outliers or biased data, which affects predictions.<br>
### Linear Discriminant Analysis
Linear Discriminant Analysis (LDA) is a supervised machine learning algorithm used for classification tasks. It is a dimensionality reduction technique that aims to find the linear combination of features that best separates two or more classes of data. LDA is particularly useful when the data has multiple features and the goal is to reduce the number of features while preserving as much of the class discriminatory information as possible.LDA is closely related to Principal Component Analysis (PCA), but unlike PCA, which is unsupervised, LDA is supervised and takes the class labels into account.<br>
**How LDA Works:** <br>
1.Compute the mean of each class and the overall mean of all data points.<br>
2.Compute the scatter matrices:<br>
   -Within-class scatter matrix: Measures how much the data points within each class deviate from the mean of their respective class.<br>
   -Between-class scatter matrix: Measures how much the class means deviate from the overall mean.<br>
3.Compute the eigenvalues and eigenvectors of the scatter matrices.<br>
4.Select the eigenvectors corresponding to the largest eigenvalues, which form the new basis for the data.<br>
5.Project the data onto this new basis, reducing the dimensionality and improving class separation.<br>
**Use Cases**: Face Recognition,Medical Diagnosis.
### Stochastic Gradient Descent
Stochastic Gradient Descent (SGD) is an optimization algorithm used in machine learning to minimize a loss function. It is particularly useful in training large models like neural networks or for datasets that are too large to fit into memory.
In SGD, instead of calculating the gradient of the entire dataset (as in traditional gradient descent), the gradient is calculated based on a single randomly chosen data point or a small batch of data points. This leads to faster updates and helps in avoiding local minima.<br>
**How SGD Works:** <br>
--Initialize Parameters: Start with random values for the model's parameters (weights).<br>
--Choose a Random Sample: Pick a random data point from the dataset.<br>
--Compute the Gradient: Calculate the gradient (partial derivatives) of the loss function with respect to the model parameters using only the chosen data point.<br>
--Update the Parameters: Adjust the parameters in the direction that reduces the error, using the computed gradient.<br>
--Repeat: Repeat the process for multiple iterations until the model converges.<br><br>
## Naive Bayes Algorithms
Naive Bayes is an algorithm that uses probabilities to make predictions. It is used for classification problems, where the goal is to predict the class an input belongs to.<br>
**How Naive Bayes Algorithm Works**
--Suppose you are a movie streaming service like Netflix and want to recommend movies to your users based on their interests. You have a dataset of movies and their genre tags, as well as information about your users’ past movie ratings.<br>
--To make recommendations, you can use the Naive Bayes algorithm. Naive Bayes is a statistical algorithm that can predict the probability of an event occurring based on the input characteristics.<br>
--For example, suppose a user has watched action and adventure movies before, and you want to recommend a new movie. In this case, the Naive Bayes algorithm will calculate the probability that the user will like a new movie based on its genre.<br>
--Naive Bayes will assume that genre tags are independent of each other, which means that the presence of one tag does not affect the presence of another tag. It is the “naive” assumption, and it simplifies the calculations. Using this assumption, Naive Bayes can calculate the probability that the user will like a movie based on the presence of each genre tag.<br>
**Advantages:**<br>
-It can handle both continuous and categorical input variables.<br>
-It is less prone to overfitting than other algorithms, which means it can generalize well on new data.<br>
**Disadvantages:**<br>
-It assumes that the input features are independent, which may not be true in all cases.<br>
-It can be sensitive to the quality of the input data, such as missing values or noisy data.<br>
