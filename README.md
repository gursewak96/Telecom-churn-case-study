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


So first, classes were assigned to all the customers in the test data set. For this, a probability cutoff of 0.5 was used. The model thus made, was very accurate (Accuracy = ~80%), but it had a very low sensitivity (~53%). Thus, a different cutoff was tried out, i.e. 0.3, which resulted in a model with slightly lower accuracy (~77%), but a much better sensitivity (~78%). Hence, you learnt that we should not just blindly use 0.5 as the cutoff for probability every time you make a model. Business understanding must be applied. Here, that means playing around with the cutoff, until we get the most useful model.

 
Also, the sensitivity of a model is the proportion of yeses (or positives) correctly predicted by it as yeses (or positives). Also, the specificity is equal to the proportion of nos (or negatives) correctly predicted by the model as nos (or negatives). For any given model, if the sensitivity increases by changing the cutoff, its specificity goes down.

![image](https://user-images.githubusercontent.com/46025020/230878827-632a8e39-fb7f-4acf-af52-66f9d5982a56.png)

High values of both cannot be achieved in a single model. Hence, we have to choose which one we would want to be higher. The safest option, though, is the one in which you just take the cutoff that equalises accuracy, sensitivity and specificity. But it totally depends on the business context. Sometimes we might want a higher sensitivity, sometimes we might want a higher specificity.

 

Also there is another view of things which was the Precision and Recall view. Those were very much related to sensitivity and specificity. Precision essentially means of the 'Yeses' predicted, how many were actually yeses. Recall on the other hand is that same as sensitivity, i.e. out of the total actual yeses, how many did you correctly predict.
