# Credit Risk Model Report

## Overview of the Analysis

In this analysis, I used various techniques to train and evaluate two models based on loan risk. I used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

My task was to predict the health of a loan--represented by `0` (healthy loan) and `1` (high-risk loan) labels--using data on loan size, interest rate, income, debt-to-income ratio, number of debt accounts, credit history, and total debt.

To conduct the analysis, I used a logistical regression model and then fit that regression model with oversampled data; and evaluated the results of each. Logitical regression was the appropriate choice for analysis because we have a discreet variable we are trying to predict (i.e. `0` for a healthy loan and `1` for a high-risk loan). Logistical regression is a supervised machine learning classification method that is helpful in predicting binary outcomes such as these.

## Results

To test the models, I constructed a confusion matrix and calculated balanced accuracy, precision, and recall scores for each model. A confusion matrix displays the true positive, false positive, true negative, and false negative figures for the model. The balanced accuracy score is helpful with imbalanced datasets such as the lending dataset used here that skews heavily towards the `0` (healthy loan) label. It is defined as the average of the recall score obtained on each class. Recall score represents the ability of a model to correctly predict the positives out of actual positives. Precision, on the other hand, measures how many model predictions are actually positive out of all positive predictions made. Below are these scores for each model.

* Machine Learning Model 1:
  
<img width="465" alt="Screen Shot 2023-05-23 at 3 18 50 PM" src="https://github.com/therahgithub/credit-risk-classification/assets/119986667/c5999c04-3138-4f3f-849d-caaa7ac7d737">

* Machine Learning Model 2:
  
<img width="462" alt="Screen Shot 2023-05-23 at 3 19 38 PM" src="https://github.com/therahgithub/credit-risk-classification/assets/119986667/e4134066-fda5-4a48-bbc5-73c402bf5f8b">
  
## Summary and Recommendations

The logistical regression used for Machine Learning Model 1 did very well predicting the `0` (healthy loan) label. However, because of the imbalanced data heavily skewed towards the `0` and with an accuracy score of just 95.3%, overall the model was subpar at predicting creditworthiness. More specifically, there are significant concerns with its ability to predict high-risk borrowers. The recall score of 91% for the `1` (high-risk loan) label indicates that too many (9%) of high-risk borrowers could slip through the process and get loans. Avoiding these types of loans is of utmost importance to lenders. So, this 9% exposes the bank to significant excess risk. Therefore, I do not recommend this model.

The logistic regression model with oversampled data used for Machine Learning Model 2 was generally superior to Machine Learning Model 1 in predicting both healthy and high-risk loans. Both models did very well predicting the `0` (healthy loan) label, but the second model achieved an overall balanced accuracy score of 99.6%; compared to 95.3 for the first. Additionally, when fit with oversampled data, this second model was statistically flawless in predicting `1` (high-risk loan) labels correctly--resulting in just one false negative. However, the precision for `1` (high-risk loan) labels of this second model is of note at 88% due to a significant number of false positives. In order to maximize profits and be a fair lender, I would like to see that metric improve so that this is a more comprehensively effective model. That said, I do recommend this model as an initial step towards risk mitigation.
