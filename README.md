# credit-risk-classification

## Overview of the Analysis

* The purpose of the analysis is to train and evaluate a logistic regression model using historical lending activity in order to predict healthy loans vs high-risk loans. 
* The dataset used included information on the loan size, the interest rate, income of the borrower, the borrowers debt to income ratio, the number of accounts and total debt outstanding, the number of derogatory marks and loan status. The loan status is the item trying to predict in order to determine if a borrower is at risk of default or not.
* The stages of the machine learning process included reading in the data from a csv file, separating the data between the features (e.g. interest rate, loan size, income, etc.) and the labels (loan status) which is the variable trying to predict based on the features of the loan/borrower. The data was split into train and test data (75% train and 25% test), which was then fit into the logistic regression model to come up with predictions of loan status on the test data. Lastly, the model was evaluated for accuracy using a confusion matrix and classification report. These steps were repeated on random data generated using the RandomOverSampler module, which was used to provide more train data on high-risk loans to improve the accuracy of the test. 
* The methods used include logistic regression model, RandomOverSample module, confusion matrix, and classification report. 

## Results

* Machine Learning Model 1: Original data separated between test and training data
  * Accuracy Score: Overall 94.4%
  * Precision Score: Overall 94%, healthy loans = 100%, high-risk loans = 87%
  * Recall Score: Overall 94%, healthy loans = 100%, high-risk loans = 89%

* Machine Learning Model 2: Resampled data was used to provide more samples of high risk loans.
  * Accuracy Score: Overall 99.6%
  * Precision Score: Overall 94%, healthy loans = 100%, high-risk loans = 87%
  * Recall Score: Overall 100%, healthy loans = 100%, high-risk loans = 100%

## Summary

Machine Learning Model 2 performs better in terms of accuracy, precision, and recall compared to Model 1. Model 2 has a significantly higher accuracy score (99.6% compared to 94.4%), and it exhibits higher recall for the high-risk loans (100% compared to 89% in Model 1).

In the context of lending and assessing loan risk, the following considerations are important:

High-risk Loans (Predicting '1's): If the main concern is correctly identifying high-risk loans (where default is more likely), Model 2 is more appropriate because it has a 100% recall score for high-risk loans. This means that it correctly identifies all high-risk loans, minimizing the chances of missing a problematic loan.

Accuracy and Overall Performance: Model 2, with its higher accuracy score, is generally a more reliable model for the dataset. However, it's essential to consider the potential consequences of false positives (healthy loans misclassified as high-risk) and false negatives (high-risk loans misclassified as healthy). Depending on the business objectives, you may have to balance these trade-offs.

Precision: Both models have the same precision for high-risk loans (87%), meaning that when they predict a loan as high-risk, they are correct 87% of the time. If precision is crucial, both models are comparable in this aspect.

In summary, if the priority is to minimize the risk of missing high-risk loans and achieve a high overall accuracy, Model 2 is the better choice. 

