# Logistic Regression 


![ml_image](machine_learning_image.png)


---
## Overview of the Analysis

Analysis of Credit Risk of borrowers with Machine learning Logistic Regression model. Credit risk inherently has imbalanced class of
data and we have had to use various techniques to train and evaluate models to deal with the imbalanced data.
In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.

This analysis was completed to assess the credit risk of borrowers. How likely are the borrowers to default on there loan?

* Explain what financial information the data was on, and what you needed to predict.

The features that we have trained our model with includes loan size, interest rate, income, debt to income, number of accounts, late
payments or derogatory marks and total debt. This is the data that we gave to the Logistic Regression model and asked it to predict
our target wich is labeled 'loan status'. Loan status is our target and basically we are trying to predict how many borrowers will default on their loan, based on the data we have provided in our features.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

We have included two prediction models in this analysis. The first was an imbalanced set of data where we had 77536 rows or individual accounts. We designated 2500 accounts as the train dataset and 75036 accounts as the test dataset.

* Describe the stages of the machine learning process you went through as part of this analysis.

The first thing to do when using Machine Learning (ML) models is prepare the data,  we designated the data for use as features and defined our target as loan status. Next we split the data using the train_test_split() function so as to designate a portion of our original dataset for training the model. Next we instatiate or create the model. In our case we set the Logistic Regression model to a variable named model. Then we fit or trained the model to the dataset we previously designated as training data. Then we predicted what the target would be with the data that we had designated as our test data. At this point our prediction has been made and we analyze the accuracy among other metrics with a accuracy score, confusion matrix and classification report.

ML commonly follows a workflow of first creating the model then fitting the model and finally predicting with the model. 

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

We used the Logistic Regression model becasue of the question we are trying to analyze. Will the lender default on there loan or not? Logistic Regression is commonly used to predict discrete outcomes, or make decisions. For example, yes or no. Default or no default.

Credit risk commonly poses classification problems becasue the data it relies on is ussually imbalanced. There are usually many more people who do not default on there loan than people that do. So if we have a group of 10,000 borrowers and 1% default, its very hard to get reliable predictions for the default class when the number of datasets is so imbalanced between the two classes, default and no-default. To help with this problem we have utilized a method of random oversampling. This is where we choose more instances in the lower weighted class training set to compensate for the smaller size of the group.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.
  - Accuracy Score was 95%
  - Precision for Healthy Loans was 100% and Precision for High-Risk Loans was 85%
  - Recall score for Healthy Loans was 99% and Recall for High-Risk Loans was 91%



* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.
  - Accuracy Score was 99%
  - Precision Score for Healthy Loans was 100% and Precision for High-Risk Loans was 84%
  - Recall for Healthy Loans was 99% and Recall for High-Risk Loans was 99%

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
The accuracy for model #1 was 95% and the accuracy for model number #2 was 99%, The accuracy measures how often the model was correct. It does so by calculating the ratio of the number of correct predictions to the total number of outcomes.
The precision measures how confident we are that the model correctly made the positive predictions. Here we can see that model #1 has a 100% precision for healthy loans and 85% for high-risk loans, that is for the times that model 1 predicted a loan would be healthy, 100% of the time they were healthy, and 85% of the times the model 1 predicted a loan would be unhealthy, they were unhealthy. We can look at it the same way for model number 2 along with the respective % above. 
Recall measures the number of actually fraudulent transactions that the model correctly classified as fraudulent. That is to say, Recall does a great job of measuring the loans that we know will default and indeed defaulted. So Recall does a good job of measuring the high-risk loans, while precision does a good job of measuring the healthy loans. What we are most concerned here is high risk loans, and becasue of that, My reccomendation is model #2 does a better job of predicting the number of healthy loans to high risk loans. We see this in the ratio of recall for high risk loans for model 2 to model 1. 99% / 91%. As well as the accuracy for model 2 is higher than model number 1. Again, becasue we are most interested in the high risk loans and predicting them correctly, I would say the measures we took in model 2 to balance the training data for the model, paid off well in the high % number we got for recall in model 2.

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

In this situation we are more interested in being able to predict whether a borrower will default for high risk loans, and because this is our interest, recall is a much more useful metric for us. We want to be able to predict out of all the high risk loans, how many can we expect to default. For this we rely on recall because recall measures the number of actually fraudulent transactions that the model correctly classified as fraudulent.
If we were interested in predicting how many healthy loans 'do not default', then I would say that precision is the more valuable metric to use. Precision measures how confident we are that the model correctly made the positive predictions. 
To answer the question, does performance depend on the problem we are trying to solve? I would say that the performance of the model varies depending on the quality of the train data we feed it, and in this case balancing the train data increased the performance of the predicting. 
In regards to the question, is it more important to predict the "1's" or the "0's"? This depends on what you are trying to acheive with the prediction model. So since we are most interested in the high risk loans and being able to accurratly predict how many there will be, we rely on recall to show us the how confident we can be in getting an idea of high risk loans actually defaulting. So yes the metrics that we use to determine if our model was usefull changes depending on what we are trying to predict. I would also say that the performance does not really depend on what we are trying to solve, but that the quality of balanced data that we train our model with plays a big role in getting quality predictions.

