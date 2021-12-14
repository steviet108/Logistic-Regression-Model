# Logistic Regression 


![ml_image](Resources/machine_learning_image.png)


---
## Overview of the Analysis

This is an analysis of Credit Risk of borrowers with Machine learning Logistic Regression model. Credit risk inherently has imbalanced class of data and we have had to use various techniques to train and evaluate models to compensate for the imbalanced data.

## Purpose

This analysis was completed to assess the credit risk of borrowers. How likely are the borrowers to default on there loan?

## Data

The features that we have trained our model with includes loan size, interest rate, income, debt to income, number of accounts, late payments or derogatory marks and total debt. This is the data that we gave to the Logistic Regression model and asked it to predict our target wich is labeled 'loan status'. Loan status is our target and basically we are trying to predict how many borrowers will default on their loan, based on the data we have provided in our features.

We have included two prediction models in this analysis. The first was an imbalanced set of data where we had 77536 rows or individual accounts. We designated 2500 accounts as the train dataset and 75036 accounts as the test dataset. The second model we created used the RandomOverSampler funtion from the imblearn.over_sampling module. Here we oversampled the minority dataset to equal the test dataset. We did this by randomly over sampling the train dataset. The result of over sampling was that we had 56271 rows of test data and 56271 rows of train data.

## Process

The first thing to do when using Machine Learning (ML) models is prepare the data,  we designated the data for use as features and defined our target as loan status. Next we split the data using the train_test_split() function so as to designate a portion of our original dataset for training the model. Next we instatiate or create the model. In our case we set the Logistic Regression model to a variable named model. Then we fit or trained the model to the dataset we previously designated as training data. Then we predicted what the target would be with the data that we had designated as our test data. At this point our prediction has been made and we analyze the accuracy with functions including accuracy score, confusion matrix and classification report. We also paid close attention to Precision and Recall to understand wich of the two models was best suited for our situation.

ML commonly follows a workflow of first creating the model then fitting the model and finally predicting with the model. 

## Methods

We used the Logistic Regression model because of the question we are trying to analyze. Will the borrower default on there loan or not? Logistic Regression is commonly used to predict discrete outcomes, or make decisions. For example, yes or no. Default or no default.

Credit risk commonly poses classification problems becasue the data it relies on is usually imbalanced. There are usually many more people who do not default on there loan than people that do. So if we have a group of 10,000 borrowers and 1% default, its very hard to get reliable predictions for the default class when the data is so imbalanced between the two classes, default and no-default. To help with this problem we have utilized a method of random oversampling. This is where we choose more instances in the lower weighted class training set to compensate for the smaller size of the group. We randomly over sample to increase the size of the dafault class to equal the non default class.

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


* Which one seems to perform best? How do you know it performs best?

The accuracy for model 1 was 95% and the accuracy for model number 2 was 99%, The accuracy measures how often the model was correct. It does so by calculating the ratio of the number of correct predictions to the total number of outcomes.
The precision measures how confident we are that the model correctly made the positive predictions. Here we can see that model 1 has a 100% precision for healthy loans and 85% for high-risk loans, that is for the times that model 1 predicted a loan would be healthy, 100% of the time they were healthy, and 85% of the times the model 1 predicted a loan would be unhealthy, they were unhealthy. We can look at it the same way for model number 2 along with the respective % above. 
Recall measures the number of loans that defaulted that were previously classified as high risk. That is to say, Recall does a great job of measuring the loans that we know will default and indeed defaulted. So Recall does a good job of measuring the high-risk loans, while precision does a good job of measuring the healthy loans. What we are most concerned here with healthy loans that default, and because of that, My recomendation is model 2 does a better job of predicting the number of healthy loans that default. We see this in the confusion matrix for the second model gave us a number of 4 loans that were predicted healthy that defaulted vrs in model 1 we saw there were 56 healthy loans that defaulted. As well as the accuracy for model 2 is higher than model number 1. I would say the measures we took in model 2 to balance the training data for the model, paid off well in the high % number we got for recall in model 2.

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

I think that its more important to predict the healthy loans that will default, because this seems the most unexpected. Therefore there were no mitigating factors worked into the loans. For example, a high risk loan is probably smaller and requires collateral and/or maybe a cosigner, whereas healthy loans are large and require less collateral, and no co-signers. So it seems to ma to the lender, a healthy loan that defaults is the most damaging and unexpected. I would want to predict this class above all else.
To answer the question, does performance depend on the problem we are trying to solve? I would say that the performance of the model varies depending on the quality of the train data we feed it, and in this case balancing the train data increased the performance of the predicting. 
In regards to the question, is it more important to predict the "1's" or the "0's"? This depends on what you are trying to acheive with the prediction model. So since we are most interested in the healthy loans and being able to accurratly predict how many will default, we are most interested in the class of borrowers that were predicted true but actually false. The "0's" and the "1's" are both important depending on what the goal is in the prediction. 

