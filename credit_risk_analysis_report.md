# Report - Credit Risk Classification Analysis

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.
The objective of the analysis is to evaluate the performance of logistic regression model in predicting credit risk associated with loans.

* Explain what financial information the data was on, and what you needed to predict.
The analysis was conducted on loan sizes, interest rate, borrower's income, debit to income ratio, number of accounts and derogratory marks and total debt, to predict loan status being '0'(healthy loan) or '1'(high_risk loan).

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).
The value counts for the y variable is '0' = 75036, '1' = 2500 which reveals imbalanced clasess since the number of healthy loan is much more than the number of high-risk loan. This can make the model lean towards healthy loans because they have more impact on accuracy.

* Describe the stages of the machine learning process you went through as part of this analysis.
  1. After reading the data into Pandas Dataframe, separate dataset into labels and features.
  2. Split data into training and testing datasets using train_test_split.
  3. Create and fit logistic regression model with the original training data.
  4. Save the predictions on the testing data labels.
  5. Evaluate the model's performance by calculating the accuracy score, generating confusion matrix, and printing classification report.
  6. Resampled the data using RandomOverSampler.
  7. Create and fit logistic regression model with resampled data.
  8. Evaluate the model's performance on the resampled data by reading the classification report.


* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).
Logistic regression model is a classification model used in supervised learning to predict discrete valued variables. Since the targeted value(y) is a binary value of '0'(healthy loan) and '1'(high_risk loan), it's best to use logistic regression to draw categorical conclusion about the data. To use this model, the data has be split into training and test set which allows us to measure the performance of the model and parameter selections with a subset of the data not used to train the model. This model is used by organizations to classify applicants properly, classify fraudulent transactions and predict market decline. Since the logistic regression model produce an accuracy of 0.94, and accuracy is known to be very susceptible to imbalanced classes. RandomOverSampler is used in resampling the data to improve the model performance. 

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

  * The Accuracy of the logistic model is 0.94 which means the model correctly predicit 94% of the classes. 
  * The precison for '0'(healthy loan) is 1.00 which means the model correctly predict true positives with no false positive, while the '1'(high_risk loan) is 0.87 which means their are some false positives included in the outcome. 
  * The recall score for the '0'(healthy loan) is 1.00, which means the model classifies true positive correctly for the healthy loan. The recall score for the (high_risk loan) is 0.89, which means the model incorrectly classifies some false positives as true positives. 

* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

  * Using the RandomOverSampler, the accuracy of the model is 0.99 which means the model perfectly predicit 99% of the classes. This shows an improvement compared to the original data.
  * The precision for both healthy loans is 1.00 while that of high_risk loans still remains 0.87 which means their are still some false positive included in the high-risk loans class. The difference in precision for both classes is 0.13 which is below 0.25 and still acceptable. 
  * The recall score for both healthy and high_risk loans is 1.00 which means the model is perfect in classifying both the healthy and high risk loan correctly.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

If you do not recommend any of the models, please justify your reasoning.
The RandomOverSampler model performed better because it has an accuracy of 0.99 compared to 0.94 accuracy of the logistic regression model trained with the original data, plus it has 1.00 recall score for both the healthy and high_risk loans. Unlike the logistioc regression model trained with the original data doing extremely well with healthy loans and lacking behind with high_risk laons predictions. It's equally important to predict correctly both the healthy and high_risk loan in order serve applicants fairly and prevent future losses for the organizations.