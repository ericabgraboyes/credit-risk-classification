# Module 12 Report Template

## Overview of the Analysis

The project objective was to develop a logistic regression model to determine the credit worthiness of a perspective loan applicant, in essence if the company offered the loan -- would the loan be classified as "healthy" or "high-risk". 
The dataset used to train the model consisted of historical lending activity from a peer-to-peer lending services company and included several features -- as shown below.

The loan status column is used to distinguish between healthy (0) loans and high-risk (1) loans.  


As displayed in the summary, the original dataset was heavily imbalanced as -- 75,036 loans were classified as healthy while only 2,500 loans were classified as high-risk.  Since the original dataset was highly imbalanced I 


Given that the data in the original dataset was heavily imbalanced, the analysis compared the difference in predictive performance for two different logistic regression models. While the models were trained using different datasets, the models actually very similar as both are scikit-learn LogisticRegression Models, and use the same features to train the model.  Where the models differ relates to the data that was used to train each model.  After splitting the data into training and testing datasets:
 * model 1: trained using original imbalanced data
 * model 2: trained using randomly oversampled data -- which had the same number of healthy and high-risk loans

After the models were trained they were used to predict on the same testing data. The results of the prediction models were analzed using scikit-learn's balance_accuracy_score, confusion_matrix, and classification_report.  The results for each model are discussed in more detail in the section below

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
