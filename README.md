# ml-mortgage-applications



# Project Background
A New York based mortgage underwriters is wanting to automate and optimize the mortgage loan application process. A business decision has been made to adopt the use of machine learning so that there is a reduction in the time and resources that are required during the application process, leading to a reduction in costs and an increase in output. 

The objective of this project is train and test a machine learning model that can accurately approve or deny a mortgage application based on the candidates application details and can be easily implemented to automate the future application process.

# Data Structure
The data used in this project consists of around 440 thousand mortgage applications from the state of New York during 2015. This data is made available due to the Home Mortgage Disclosure Act (HMDA) which requires information about mortgages to be publicaly disclosed by financial institutions. 

The dataset is avaiable on [Kaggle](https://www.kaggle.com/datasets/jboysen/ny-home-mortgage).



# Data Preparation

The stages of data preparation were then made into a preprocessing pipeline, ensuring that preprocessing stage is easily replicable.


# Model
The model selection process involved using cross validation to select the classifier that performed best, using f1 score as the evaluation metric. Although Catboost was the highest performing classifer, it was decided to use XGBoost as the classifier as it scored closely on the cross validation test and is a more efficient model when optimising hyperparemeters. 

To further improve the performance of the model, a two-step process was followed to optimise the models hyperparemeters. First, a randomized search was conducted to return the parameters that return the highest cross-validation score. The next step was to run a grid search cross-validation test, based on the parameters that were returned from the first randomized search. 

As a result of hyperparameter optimization, the cross-validation f1 score for the XGBoost model increased from 0.7674 to - -.



# Evaluation
