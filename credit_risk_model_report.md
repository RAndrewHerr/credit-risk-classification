# Credit Risk Model Report

## Overview of the Analysis

In this analysis, I used various techniques to train and evaluate two models based on loan risk. I used a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

My task was to predict the health of a loan--represented by `0` (healthy loan) and  `1` (high-risk loan) labels--based on a borrower's loan size, interest rate, income, debt-to-income ratio, number of debt accounts, credit history, and total debt.

To conduct the analysis, I used a logistical regression model and then a second logistical regression model fit with oversampled data.

## Results

To test the models, I calculated balanced accuracy, precision, and recall scores for each model. Balanced accuracy in binary is helpful with imbalanced datasets such as these lending data that skews heavily towards the `0` (healthy loan) label. It is defined as the average of recall obtained on each class. Recall is the ratio of correctly predicted positive observations to all predicted observations for that class (in this context, 

* Machine Learning Model 1:
  * Accuracy 
  * Precision
  * Recall

* Machine Learning Model 2:
  * Accuracy 
  * Precision
  * Recall

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.

The logistical regression model did very well predicting the `0` (healthy loan) label. However, because of the imbalanced data heavily skewed towards the `0` and with an accuracy score of just 95.3%, overall the model was subpar at predicting creditworthiness. More specifically, there are significant concerns with its ability to predict high-risk borrowers. The recall score of 91% for the `1` (high-risk loan) label indicates that too many (9%) of high-risk borrowers could slip through the process and get loans. Avoiding these types of loans is of utmost importance to lenders. So, this 9% exposes the bank to significant excess risk. 

The logistic regression model with oversampled data was generally superior to the logistic regression model alone in predicting both healthy and high-risk loans. Both models did very well predicting the `0` (healthy loan) label, but the second model achieved an overall accuracy score of 99.6%; compared to 95.3 for the first. Additionally, when fit with oversampled data, this second model was statistically flawless in predicting `1` (high-risk loan) labels correctly--resulting in just one false negative. However, the precision for `1` (high-risk loan) labels of this second model is of note at 88% due to a significant number of false positives. In order to maximize profits and be a fair lender, I would like to see that metric improve. 
