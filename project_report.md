# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### SOUMILI CHAKRABORTY

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
I realized that the prediction submission format had to comply with the exact Kaggle submission format, with datetime and count columns. Model outputs needed postprocessing to set any predictions below zero to zero and to re-order predictions as per the test set; otherwise, they were disqualified from submission for failure to comply. 

### What was the top-ranked model that performed?
The best-performing model in this bike-sharing prediction task was the **WeightedEnsemble_L3**, achieving the lowest RMSE score of **33.94** on validation data. This ensemble approach outperformed all individual models by combining predictions from multiple base learners to optimize accuracy.

## Exploratory data analysis and feature creation
### What did the exploratory analysis find, and how did you add additional features?
A glance at the data showed a few strong demand patterns for bikes concerning the hour, day, and weather conditions. To capture those effects, I extracted year, month, day, and hour from the datetime column as new features to help the model learn about temporal trends and hence become stronger in predictions. 

### How much better did your model perform after adding additional features, and why do you think that is?
Adding features improved the kaggle score from 1.80 to 0.47. This was one leap of improvement since the new features made the model better able to learn on daily and seasonal patterns in bike use and fit those observations.

## Hyper parameter tuning
### How much better did your model perform after trying different hyperparameters?
Further hyperparameter optimization brought the RMSE to around 37 for the best-tuned model. The new hyperparameters may have caused the model to overfit the training data or underfit the overall patterns, leading to worse performance on validation data. This suggests the new model has higher bias but better variance, as it has better generalization on the data.

### If you were given more time with this dataset, where do you think you would spend more time?
With more time, I would attempt more advanced feature engineering and try to find more new features from the dataset, since introducing new features and removing independent features led to better results.

### Create a table with the models you ran, the hyperparameters modified, and the Kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|prescribed_values|prescribed_values|presets: 'best_quality'|1.80193|
|add_features|prescribed_values|prescribed_values|presets: 'best_quality'|0.47081|
|hpo|GBM: num_boost_round, num_leaves, extra_trees (XT)|NN_TORCH: learning_rate, activation, dropout_prob|presets: 'best_quality'|0.55786|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top Kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
The project is focused on bike-share demand prediction, using techniques such as data exploration, feature engineering, and machine learning. The initial model, which was set with default features and parameters, gave the baseline score. The addition of time-based features (year, month, day, hour) to the data allowed the models to recognize and capture important temporal patterns, thereby significantly improving model performance. Further, hyperparameter optimization led to better generalization of the model. Alternating these steps is important to reach a reasonable value for validation and test errors.
