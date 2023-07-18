# Credit Risk Classification
This is analysis of logistic regression models of consumer credit risk.

### Split the Data into Training and Testing Sets
A Pandas DataFrame is created by reading lending_data.csv (in the Resources folder).

The target (y) variable, “loan_status”, is separated from the other (X) features. Sklearn's train_test_split function is applied to split the data into training and testing datasets.

### Create a Logistic Regression Model with the Original Data
An sklearn logistic regression with is fit to the training data. A limited-memory Broyden–Fletcher–Goldfarb–Shanno solver is used by setting the solver parameter to 'lbfgs' when instantiating the sklearn LogisticRegression().

After the model is fitted on the training data, predictions are made on the X_test data.

The model’s performance is evaluated through its balanced accuracy score, a confusion matrix, and classification (all from sklearn). 

### Create a Logistic Regression Model with Resampled Data
The data is then resampled using imblearn's RandomOverSampler.

A logistic regression model on the resampled data is then implemented and evaluating following the steps above. 
