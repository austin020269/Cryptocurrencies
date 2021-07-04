# Cryptocurrencies

UT Bootcamp Module 18 Challenge

## Project Overview
Use unsupervised machine learning methodology to investigate a dataset of different cryptocurrencies and develop trends to deliver investment possibilities to Martha's firm, Accountability Accounting.  During this process, we learned how to cluster, transform and process data as well as reduce its dimensions and compenents using PCA.

## Resources
Data Sources provided to analyze and minipulate included:
- crypto_data.csv

Software utilized for this study included: 
- Python 3.7.6 
- Conda 4.9.2 
- Jupyter Notebook 6.1.4
- Personal GitHub account

## Analysis and Workflow
The general workflow in running these models are to :
1. Read and clean the data
2. Split the data into training and testing
3. Resample the data according to the algorithm method (SMOTE, Naive Random, Undersampling, etc.)
4. Run the confusion matrix and show statistical results

### Deliverable 1: Resampling Models to Predict Credit Risk

Specifically for this deliverable we did the following:
1. Create the training variables by converting the string values into numerical ones using the get_dummies() method.
2. Create the target variables.
3. Check the balance of the target variables.
4. Use the LogisticRegression classifier to make predictions and evaluate the model’s performance.
5. Calculate the accuracy score of the model.
6. Generate a confusion matrix.
7. Print out the imbalanced classification report (see below).

Naive Random Oversampling:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_1a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_1.PNG)
- Accuracy Score: 67.2%
- Precision High Risk: 1%
- Precision Low Risk: 100%
- Recall High Risk: 69%
- Recall Low Risk: 65%

SMOTE Oversampling:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_2a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_2.PNG)
- Accuracy Score: 67.1%
- Precision High Risk: 1%
- Precision Low Risk: 100%
- Recall High Risk: 70%
- Recall Low Risk: 64%


Undersampling:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_3a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli1_3.PNG)
- Accuracy Score: 51.7%
- Precision High Risk: 0%
- Precision Low Risk: 100%
- Recall High Risk: 59%
- Recall Low Risk: 44%


### Deliverable 2: Use the SMOTEENN algorithm to Predict Credit Risk

Specifically for this deliverable we did the following:
1. Use the credit_risk_resampling.ipynb file to create your training and target variables.
2. Resample the training data using the SMOTEENN algorithm.
3. Use the LogisticRegression classifier to make predictions and evaluate the model’s performance.
4. Calculate the accuracy score of the model.
6. Generate a confusion matrix.
7. Print out the imbalanced classification report (see below).

SMOTEEN - Combination (Over and Under) Sampling:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli2_1a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli2_1.PNG)
- Accuracy Score: 68.1%
- Precision High Risk: 1%
- Precision Low Risk: 100%
- Recall High Risk: 76%
- Recall Low Risk: 60%


### Deliverable 3: Use Ensemble Classifiers to Predict Credit Risk
Specifically for this deliverable we did the following:
1. Create the training variables by converting the string values into numerical ones using the get_dummies() method.
2. Create the target variables.
3. Check the balance of the target variables.
4. Resample the training data using the BalancedRandomForestClassifier algorithm with 100 estimators.
5. Calculate the accuracy score of the model
6. Generate a confusion matrix
7. Print out the imbalanced classification report (see below).

Balanced Random Forest Classifier:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_1.PNG)
- Accuracy Score: 64.8%
- Precision High Risk: 56%
- Precision Low Risk: 100%
- Recall High Risk: 30%
- Recall Low Risk: 100%

9. Print the feature importance sorted in descending order (from most to least important feature), along with the feature score.
10. Resample the training data using the EasyEnsembleClassifier algorithm with 100 estimators.
11. Calculate the accuracy score of the model
12. Generate a confusion matrix
13. Print out the imbalanced classification report (see below).

Easy Ensemble Classifier:
![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_2a.PNG)

![alt text](https://github.com/austin020269/Credit_Risk_Analysis/blob/main/Deli3_2.PNG)
- Accuracy Score: 92.3%
- Precision High Risk: 6%
- Precision Low Risk: 1%
- Recall High Risk: 91%
- Recall Low Risk: 94%

### Deliverable 4: Written Report on the Credit Risk Analysis
Whether a model can predict if a loan is high risk or not would be determined by the value of it's high risk recall rate.  The higher the rate, the fewer high risk loans that are approved.  Our top three performing models for this statistic are :
1. Easy Ensamble Classifying (91%)
2. SMOTEENN Sampling (76%)
3. SMOTE Oversampling (70%)

Additionally, another import feature of our models is it's accuracy, reflecting it's dependability in reference to the true or accepted value.  The top three for this statistic are:
1. Easy Ensemble Classifying (92.3%)
2. SMOTEENN Sampling (68.1%)
3. Naive Random Oversampling (67.2%)

