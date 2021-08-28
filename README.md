# Car-Dataset-Multiple-Regression-using-Python
Using python, built multiple linear regression model based on the dataset related car sales.

**Introduction**

This report details the logistic regression analysis conducted for the marketing department of the dealership with the aim of predicting which potential clients are likely to participate in a vehicle purchase and which are not. The results of this analysis aim to support efforts by the marketing team in the pursuit of objectives relating to branding, engagement, and profit generation.  

The analysis preparation included a review and visualization of the dataset including the removal of incomplete records and creation of indicator variable sex_Male to replace ‘sex’. Correlation between the predictors and the response were analyzed using plots and tabulated values. Eight models were produced encompassing all combinations of the variables and were assessed for predictor significance and overall fit. Then, all models were used for prediction and evaluated on such. The best model was chosen based on the accuracy of the test prediction. 


**Analysis** 

Part 1. Data preparation and visualization

In preparation of the analysis the data was reviewed prior to being read into python. All records containing nulls were removed and an indicator (dummy) variable was created for the categorical variable ‘sex’. In addition, the categorical response ‘purchase’ and interval variable age, were assigned integer types. 

Once complete, plots of predictor variables ‘age’ and ‘income’ as well as the frequency of predictor ‘sex’ were examined. The overall distribution of age is Gaussian and possibly a bit platykurtic. For income, we see evidence of right skewness and platykurtic characteristics with a rough bell-curve shape. The joint plot of ‘income’ and ‘age’, shows a slightly positive relation. Examining the frequency of ‘sex’ we see an approximately equal split between Male and Female.

Correlation between predictor variables is represented in the correlation matrix and pair plot. A moderately positive correlation is present between the response and predictor ‘income’ at 0.336978. This predictor also shares a slight positive correlation with ‘age’. Predictor variable ‘sex_Male’, the indicator created for categorical variable ‘sex’, has low correlation with all other predictors and the response. The predictor with the highest correlation to the response is ‘age’ with a highly positive correlation of 0.632383. As such, it may be functional in predicting response variable ‘purchase’.

Part 2. Inference by logistic regression

The following sub-section will examine coefficient interpretations and the model fit for each model produced. The odds is the relative likelihood of a purchase vs not purchase: for example, an odd of 1.5 means that chance of a purchase is 1.5 times of that of a non-purchase. The pseudo R-squared value is the ratio of the log-likelihoods for the null and full model, and is meant to act similarly to the R-square value in linear regression models (unknown, n.d.). Since this value increases monotonically with the number of predictor variables fit will be assessed using deviance, which is the maximized log likelihood multiplied by negative two (Gareth James et al., 2017). When examining deviance, a smaller value signifies a better fit. 


Part 3 & 4. Prediction and Evaluation

This section will examine the prediction performance of all models. It's useful to define the following key terms:
	Accuracy: percentage of correct predictions of all predictions
	Precision: percentage of correct predictions of all predictions of a specific class (purchase or not)
	Recall: percentage of correct predictions of each actual class (percentage of the actual purchase/not purchase that were correctly predicted)


**Final Model Chosen**

Model with all variables [“modelful”]
Training Dataset 

•	Based on the total of “no purchases” classes (purchase =0) predicted, the model predicted 186 cases correctly (True negatives) out of total 217 predictions, resulting in 86 percent precision. Based on the total number of actual “no purchases” class of 198, 186 of them have correctly been identified, resulting in 94 percent recall. 
•	For the total of “purchases” classes (purchase = 1) predicted, 77 (true positives) out of 89 predictions were accurate resulting in 87 percent precision. Based on the 108 “purchases” class, 77 of them were captured by the model, resulting in 71 percent recall. 

Test Dataset

•	Based on the total of “no purchases” classes (purchase =0) predicted, the model predicted 66 cases correctly (True negatives) out of total 78 predictions, resulting in 85 percent precision. Based on the total number of actual “no purchases” class of 73, 66 of them have correctly been identified, resulting in 90 percent recall.
•	For the total of “purchases” classes (purchase = 1) predicted, 47 (true positives) out of 54 predictions were accurate resulting in 87 percent precision. Based on the 59 actual “purchases” class, 47 of them were captured by the model, resulting in 80 percent recall. 

Overall, the model performed extremely well on both the train dataset and the test dataset. The predictions on the train dataset seemed to capture “no purchases” classes better at 94 percent compared to 90 percent on the test dataset while the predictions on the test dataset performed better on the “purchase” class at 80 percent compared to 71 percent on the train dataset.

Model Comparison

Comparing the results of the model against other models, the overall accuracy of the models is the highest at 86 percent. However, the model seems to capture the “no purchase” classes exceptionally well at 94 percent while capturing a relatively low amount of “purchase” classes at 71 percent. Regardless of their differences, results show that the model is able to predict both classes accurately in comparison to other models.


**Conclusion & Recommendations**

The worst models are the null model (without predictors) and the model with only sex variable. Both models have predicted all purchase class to be 0, resulting in lowest accuracy scores of all models in training and test data. Although these two models in enjoy 100% recall in class 0 with all predicted class 0, the precision in class 0 is only 65% in train set and 55% in test set, with 0% precision and 0% recall in class 1 in train and test set. The fact that the model with only sex as predictor is performing so poorly confirms with the finding in full model, where sex is the only insignificant predictor at 5% level (p value greater than 0.05).

The best model is the full model, with highest accuracy score of 86% in train and test set. The full model also enjoys highest precision in train and test set across all models but falls behind on recall when comparing to the model with no age predictor.

Based on the statistical evidence and prediction result in this report, we recommend the following best practices:
	Design user-friendly customer surveys to effectively identify customers’ age and income level (both age and income predictors are significant and increase model performance).
	Devise targeted marketing materials that attract higher age and income customers who are found to be more likely to make a car purchase in this analysis. 

