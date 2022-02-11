# Project 2 - Ames Housing Data and Kaggle Challenge



# Problem Statement: 
Our real estate agency in Ames, Iowa, is working on a solution to help our in-house real estate agents in comparative market analysis to determine a fair and competitive offering price. With our model, we plan to support our in-house real estate agents in the following areas:

1) offer proprietary estimate of a property’s value based on the key features of the property

2) a useful reference point in assessing the fairness of a home’s price



# The Modelling process 

Before Modelling, these are the follow steps taken in preparing the data for modelling. 

1) Data Cleaning, working with null values, outliers, removing rows, columns, imputing values

2) Exploratory Data Analysis of categorical and numerical features 

3) Multicollinearity, feature engineering, one-hot encoding

4) Modelling 

5) Improve Model through hyperparameter tuning and feature selection 


# Conclusion
### Four different models were tested on training data:

1) Linear Regression

2) Ridge CV

3) lasso CV

4) elastic net regression


Looking at the Kaggle score of the different models, we can see that the RMSE score is lowest for LassoCV. Top 25 coefficients were extracted to see the top features affecting the lasso coefficients in the prediction of sale prices. 

The top 25 features are in categories related to Area, Quality/ Condition, Location, Age, External Features and Building Type. 


### Model Tuning

Improvements were made to improve the model in two areas. 

1) Hyperparameter tuning  

Improved the model by selecting the best configurations of the hyperparameters that give us the best model performance output. 

2) Feature Selection 

After determining the important features in the LassoCV model, I decided to run another model with just the important features identified in the initial model, discarding the other features to see if there was an improvement in the results. 


After rerunning the model, it was noticed that the LassoCV results improved after hyperparameter tuning with a R2 of 0.93.This model will be used to predict the housing prices in Ames based on the characteristics of the house. This model will support out in-house real estate agents support the clients (buyers & sellers) by looking at the key factors affecting housing prices in areas of Area, Condition/Quality, Building Type, External Feature and Location. With better pricing estimates, the real estate agents can advice buys on the estimate selling price and how they are able to improve their property features to push for a higher selling price. Furthermore for buyers, real estate agents will be able to work with buyers in determining the fair value of a house price in relation to the features of the house. 

# Recommendations

More time will be required to drop more features to improve the model, testing across other machine learning models before the solution will be able to be released for implementation to help the real estate agents in predicting the Sale Prices depending on the features of the house. If the model is continually worked on, collecting more data from different cities within the USA with a longer time frame, this dataset will serve more purpose beyond Iowa, benefitting more individuals and also showing more valuable trends between housing prices in different cities. Furthermore, there are also some limitations with the model as the model currently only considers the features of the property only, it does not take into account other factors including econommic indicators, government policies, mortgage and interest rates. 

