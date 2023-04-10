# Telecom churn case study

## Problem Statement

You have a telecom firm which has collected data of all its customers. The main types of attributes are:

- Demographics (age, gender etc.)
- Services availed (internet packs purchased, special offers taken etc.)
- Expenses (amount of recharge done per month etc.)

Based on all this past information, you want to build a model which will predict whether a particular customer will churn or not, i.e. whether they will switch to a different service provider or not. So the variable of interest, i.e. the target variable here is ‘Churn’ which will tell us whether or not a particular customer has churned. It is a binary variable - 1 means that the customer has churned and 0 means the customer has not churned.

## Summary

 the steps that were performed throughout the model building and model evaluation were:
 1. Data cleaning and preparation
   - Combining three dataframes
   - Handling categorical variables
       - Mapping categorical variables to integers
       - Dummy variable creation
   - Handling missing values
2. Test-train split and scaling
3. Model Building
  - Feature elimination based on correlations
  - Feature selection using RFE (Coarse Tuning)
  - Manual feature elimination (using p-values and VIFs)
4. Model Evaluation
  - Accuracy
  - Sensitivity and Specificity
  - Optimal cut-off using ROC curve
  - Precision and Recall
5. Predictions on the test set
