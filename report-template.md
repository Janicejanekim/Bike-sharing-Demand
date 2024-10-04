# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### NAME HERE
Jane Kimani

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
i realised that to submit the output it had to be positive values for the predicted demand. the model had predicted some negatuive values. To address the issue i had to transform the negative values by setting all negative predictions to positive predictions that is to be zero, then set them to  prediction dataframe, save and submit it.
### What was the top ranked model that performed?
the top performing model from the fit_summary was WeightedEnsemble_L3 with score of 0.914985

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
we used histogram to visualise the dataset that we noticed that certain features like date-time might have a significant impact bike demand. so we created the new feature 'hour' by extracting it from the date column. the feature helped to captures variations in demand based on different time demand.

### How much better did your model preform after adding additional features and why do you think that is?
After adding the the 'hour' feature, the model performance notably improved. This was attributed by the capturing of the time dependent variations in the bike demand. By encoding the date-time, our model gained valuable insights into patterns leading to more accurate predictions.
## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
The hyperparameter tuning process significantly improved the the model performance. We utilized a random search strategy (searcher='random') over 10 trials (num_trials=10) to identify optimal hyperparameters for each model. This process led to a noticeable enhancement in the model's validation score (root mean squared error), as demonstrated by the leaderboard.
Notably, the top-performing model after hyperparameter tuning was the WeightedEnsemble_L2, achieving a validation score of approximately -34.87. 

### If you were given more time with this dataset, where do you think you would spend more time?
 Continue fine-tuning hyperparameters based on a more exhaustive search strategy, such as grid search or Bayesian optimization. Exploring a wider range of hyperparameter values and combinations could unveil additional opportunities for model improvement.
### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|600|default|default|	0.914985|
|add_features|600|default|default|	0.972123|
|hpo|1000|learning rate|layers|-34.867196|



### Create a line plot showing the top model score for the three (or more) training runs during the project.



![model_train_score.png](cd0385-project-starter/project/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.


![model_test_score.png](cd0385-project-starter/project/model_test_score.png)

## Summary
predicting bike sharing demand using AutoGluon was successful, showcasing the impact of feature engineering and hyperparameter optimization on model performance. By systematically refining our model and dataset, we achieved competitive results on Kaggle.