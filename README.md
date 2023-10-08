# LinearRegression_Pipeline
Returns the best fitting linear regression model with its associated hyperparameters. Fits a regular linear, ridge, lasso, and ElasticNet regressions.
The same parameters are used for each of the regressions aside from the estimator.

Prerequisites: A cleaned, ready to run pandas dataframe with continuous and/or ordinal categorical columns of data. This file was not created to support binary predictor variables or non-ordinal categorical data. If necessary, you can create dummy variables and add them to the X - predictors after scaling is completed.

Multicolinearity is assessed via correlation heat maps and pair-wise scatterplots, and must be adressed manually. If strong correlations are detected between predictors, it is up to you whether or not to drop those variables. This script will run without dropping them.

Pearsonr P-values will be calculated between each predictor and the outcome, and predictors with a p-values > 0.05 will be dropped prior to analysis. If there are no remaining predictors, an error will be raised and you can decide whether or not to proceed by not dropping the insignificant predictors (manually).

Values are already filled in for the test set size (20%), random state (33), alpha values (see list), and number of cross-validation (CV) folds (5), but all these variables can be found at the top of the script and can be altered prior to running. The two variables that MUST be filled in are the DF you wish to use (import from wherever you wish so long as it is prepared/clean), and a string varible which stores the name of the outcome column.

The output will display all of the models with their RMSE values, along with their associated hyperparameters, a DF with the true test set outcome values, predicted values using the model that minimizes the RMSE, and the difference between the two in percent, and the mean, SD, max, and minimum absolute percent difference for the best model predictions.
