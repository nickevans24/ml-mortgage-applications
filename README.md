# ml-mortgage-applications

# Project Background
A New York based mortgage underwriters is wanting to automate and optimize the mortgage loan application process. A business decision has been made to adopt the use of machine learning so that there is a reduction in the time and resources that are required during the application process, leading to a reduction in costs and an increase in output. 

The objective of this project is train and test a machine learning model that can accurately approve or deny a mortgage application based on the candidates application details and can be easily implemented to automate the future application process.

# Data Structure
The data used in this project consists of around 440 thousand mortgage applications from the state of New York during 2015. This data is made available due to the Home Mortgage Disclosure Act (HMDA) which requires information about mortgages to be publicaly disclosed by financial institutions. 

The dataset is avaiable on [Kaggle](https://www.kaggle.com/datasets/jboysen/ny-home-mortgage).

The data primarily consists of categorical features that relate to the profile of the application, such as gender, race, and county as well as features that categorise the loan, such as loan type, loan purpose, and property type. Examples of continuous features include the loan amount, applicant income, and the median family income of the county the property resides in. 

# Data Preparation
The initial stage of data preparation was to find the correlation of features to the target variable, removing those that had a low correlation coeeficients (association scores for categorical features) to reduce the chance of overfitting in the model. After this, all categorical features were encoded using one-hot encoding. Cross validation tests were also used to investigate whether log transformations and scaling of skewed features improved the cross validation score of the model, but as there was no benefit they were not required for preprocessing.  
The stages of data preparation were then made into a preprocessing pipeline, ensuring that preprocessing stage is easily replicable.

# Model
The model selection process involved using cross validation to select the highest performing classifier, using f1 score as the evaluation metric. Although Catboost was the highest performing classifer, it was decided to use XGBoost as the classifier as it scored closely on the cross-validation score and is a more efficient model when optimising hyperparemeters. 

To further improve the performance of the model, a two-step process was followed to optimise the models hyperparemeters. First, a randomized search was conducted to return the parameters that return the highest cross-validation score. The next step was to run a grid search cross-validation test, based on the parameters that were returned from the first randomized search. 

As a result of hyperparameter optimization, the cross-validation f1 score for the XGBoost model increased from 0.7674 to 0.7741.

# Evaluation
The business requirement for this project was to create a model that can accurately approve or deny a mortgage application. The final model was returned a precision score of 82.66% with an F1 score of 0.7754. The accuracy of the model, and the implementation of the preprocessing pipeline, helped to achieve the business case of creating an accurate model that can easily be implemented with new data to help improve the mortgage application process for the mortgage underwriters.

