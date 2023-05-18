# Credit-Risk-Classification-Template

## Overview of the Analysis

The project objective was to develop a logistic regression model to determine the credit worthiness of a perspective loan applicant, in essence if the company offered the loan -- would the loan be classified as "healthy" or "high-risk". 
The dataset used to train the model consisted of historical lending activity from a peer-to-peer lending services company and included several features -- as shown below.

**Features used in model to predict loan status:<br>**
![Summary DataFrame displaying all features used in predicting loan status](/Images/features-dataframe.png)

The loan status column is used to distinguish between healthy (0) loans and high-risk (1) loans.  


As displayed in the summary, the original dataset was heavily imbalanced as -- 75,036 loans were classified as healthy while only 2,500 loans were classified as high-risk.  Since the original dataset was highly imbalanced I 


Given that the data in the original dataset was heavily imbalanced, the analysis compared the difference in predictive performance for two different logistic regression models. While the models were trained using different datasets, the models actually very similar as both are scikit-learn LogisticRegression Models, and use the same features to train the model.  Where the models differ relates to the data that was used to train each model.  After splitting the data into training and testing datasets:
 * model 1: trained using original imbalanced data
 * model 2: trained using randomly oversampled data -- which had the same number of healthy and high-risk loans

After the models were trained they were used to predict on the same testing data. The results of the prediction models were analzed using scikit-learn's balance_accuracy_score, confusion_matrix, and classification_report.  The results for each model are discussed in more detail in the section below

## Results
* Machine Learning Model 1: Trained on original, imbalanced data:
    * Balanced accuracy score = 0.95204792
    * Healthy-loans:
        * Precision score: 1.00 -- of all the loans the model predicted to be healthy; 100% of them were actually healthy.
        * Recall score: 0.99 -- of all the loans to actually be classified as healthy, the model predicted this outcome correctly for 99% of the loans
        * F1-score: 1.000 -- indicates that the model does a good job of predicting the loan status of healthy loans
      
    * High-Risk loans:
        * Precision score: 0.85 -- of the loans the model predicted to be high-risk; 85% of them were actually high-risk
        * Recall score: 0.91 -- signifies that out of all the loans to actually be classified as high-risk, the model predicted this outcome correctly for 91% of the loans.
        * F1-score: 0.88 -- indicates that the model does a reasonable job of predicting the loan status of high-risk loans. The drop in precision vs. recall suggests that the model slighly over-estimates how many high-risk loans there are

**Confusion matrix - Original imbalanced dataset:**<br>
    ![Confusion matrix shows healthy loans (18663 to 102) and high-risk loans (56 to 563)](/Images/original-confusion-matrix.png)

* Machine Learning Model 2: Trained on randomly oversampled data:
    * Balanced accuracy score: 0.99367812
    * Healthy-loans:
        * Precision score: 1.00 -- of all the loans the model predicted to be healthy; 100% of them were actually healthy.
        * Recall score: 0.99 -- of all the loans to actually be classified as healthy, the model predicted this outcome correctly for 99% of the loans
        * F1-score: 1.000 -- indicates that the model does a good job of predicting the loan status of healthy loans
      
    * High-Risk loans:
        * Precision score: 0.84 -- of the loans the model predicted to be high-risk; 84% of them were actually high-risk
        * Recall score: 0.99 -- signifies that out of all the loans to actually be classified as high-risk, the model predicted this outcome correctly for 99% of the loans.
        * F1-score: 0.91 -- indicates that the model does a reasonable job of predicting the loan status of high-risk loans. The drop in precision vs. recall suggests that the model slighly over-estimates how many high-risk loans there are
        
**Confusion matrix - randomly oversampled data:<br>**
    ![Confusion matrix shows healthy loans (18649 to 116) and high-risk loans (4 to 615)](/Images/oversampled-confusion-matrix.png)

## Summary
When thinking about the business/real-world implications I would maintain that the focus of the model should be on predicting high-risk loans vs. low risk or healthy loans.  The implications to a small bank could be much more impactful if they are unable to predict risky loans vs healthy loans.  Keeping this in consideration I would recommend using the over-sampled model (if we had to use one of the two models), since the recall improved from 0.91 to 0.99 and only came at the cost of reducing the precision by .01.  Overall the loss in precision is pretty minor given the precision score is still relatively high at 0.84.

Items to consider before "fully embracing" the model is that it would make sense to run the analysis with a validation dataset; which has not been done in the initial analysis.  Another item to consider is the need to check for overfitting to the data -- which also was not done in the initial analysis.  
