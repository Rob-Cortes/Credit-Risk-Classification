# Credit Risk Classification

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
* Explain what financial information the data was on, and what you needed to predict.
* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
* Describe the stages of the machine learning process you went through as part of this analysis.
* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

This is an assessment of the ability of logistic regression models to predict consumer credit risk. While there are numerous credit metrics already in use in the industry, no methodology is perfect, and the consequences of misjudging consumer credit risk can be severe, as demonstrated in 2007-2008. It is therefore worthwhile to evaluate and refine existing methods of credit analysis, as we will do in this report.

Our assessment relies on data from a peer-to-peer lending services company. The data contains 77,536 observations, with each observation consisting of:

* Loan size
* Interest rate
* Borrower income
* Debt/income ratio
* Number of accounts
* Number of derogatory marks
* Total debt

We evaluate two logistic regressions of the above metrics on our target metric, loan status, which is equal to 0 when a loan is healthy and 1 when a loan is high risk. These logistic regressions come from the sklearn.linear_model library, and rely on the limited-memory Broyden–Fletcher–Goldfarb–Shanno (LBFGS) solver. The first logistic regression is performed on the original data; the second is performed on resampled data, with the random over-sampler function from the imbearn.  

## Results

The findings of this analysis are as follows:  

* Logistic Regression on Original Data:
  * Balanced accuracy score of 95.2%
  * Precision of 99% (weighted avg)  
  * Recall of 99% (weighted avg)

* Logistic Regression on Resampled Data:
  * Balanced accuracy score of 99.4% 
  * Precision of 99% (weighted avg)
  * Recall of 99% (weighted avg)

## Summary

Both models perform well, as demonstrated by the balanced accuracy scores of 95.2% (original data) and 99.4% (resampled data). The resampling model's higher balanced accuracy score means that this model is more accurate when adjusting to make class-balanced sample weights. The resampling model has marginally worse precision on high-risk loans (84% vs 85%), however this is outweighed by its superior recall on high-risk loans (99% vs 91%). This, in our view, is the most important metric for evaluating model performance. The loss from a defaulted loan has more of an impact than the income from a successfully matured loan. Therefore, the most value to be gained from these models comes from flagging loans that are true high-risk loans. This is what the resampling model provides, at the minor cost of slight over-flagging when compared to the original model. For this reason we recommend the resampling model. 