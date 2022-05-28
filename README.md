# King County Housing Analysis with Multiple Linear Regression.

Author: Kyunghwan William Kim 

## Overview

A young couple is planning on selling their home, they want to increase the home value as much as possible but have limited capital for renovations. The couple decided to use Multiple Linear Regression Modeling to analyze and predict house sales in King County based on certain features or variables, so that they can be used to make profitable decisions. 

After careful evaluation and various iterations of our linear regression models, we have determined that square feet of living space and building grade are the most correlated with a higher selling house price.

## Business Problem

Our stakeholders are seeking advice for new homeowners about how home renovations might increase the estimated value of their homes and by what amount.

This analysis will help homeowners buy and/or sell homes. We will be reviewing building grade and square-footage of living space and various factors to determine which features are highly correlated with home sale prices.

### Hypothesis

Null Hypothesis - There is no relationship between our independent variables and our dependent variable (target)

Alternative Hypothesis - There is a relationship between our independent variables and our dependent variable (target)

### Questions to be analyzed

Q1: What features have the highest correlation to the home price?

Q2: What features have the strongest correlations with other predicting variables?

Q3: What combinations of features is the best fit for price predictions?

## Data Understanding

The data used for this analysis is the King County Housing data set. The data set contained information and features for more than 21,000 homes in King County. Each home in the set contained information regarding features such as number of bedrooms/bathrooms/floors, square footage of living space and lot, zip-code, building grade, condition and etc.

## Methods

The data was explored and invesigating using the fundamentals of EDA. Object datatypes have been transformed into integers using the split function or mapping. We then removed unnecessary data such as duplicates and irrelevant columns. We removed outliers when appropriate by removing outliers that were about 3 standard deviations from the mean, depending upon the criteria we were reviewing. We utilized descriptive statistics as well as visualizations to illuminate trends in the data and isolate key factors for developing profitable homes. We then built multiple linear regression models to determine our strongest correlations, and used an iterative approach to our model-building. We evaluated each model and then returned to the data repeatedly to see what could to be added, changed, or removed to achieve a more successful model.

## Results


### Visual 1
![fig1](./images/grade vs price.png)

There is a positive correlation between building grade and home sale price. As the grade designation increases (scale of 1-13), house price also increases.


![fig2](./images/sqft_living vs price.png)

There is a positive correlation between square-feet of living space and home sale price. As sqare-footage of living space increases, house price increases.

##### Q1: What features have the highest correlation to the home price?

The houses grade, sqft_living, and bathrooms have the highest correlation with price.

##### Q2: What features have the strongest correlations with other predicting variables?¶

None of our features have a correlation over 0.75 so multicollinearity is not an issue. Sqft_livng and grade have the highest correlations in our data.

##### Q3: What combinations of features is the best fit for price predictions?

Grade, sqft_living and bathrooms are the best fit for a multiple regression model. These features are highly correlated with price, have relatively low multicollinearity, and can together account for more than half of the variability of price. All multiple regression assumptions are satisfied with these features included.

## Modeling

Total of 6 Models were created to predict housing prices. Below is a summary of the model results

##### Model #1
Baseline Model: Using two features most correlated to price
R2: 0.486
##### Model #2
Train_test_split and Onehotencoding on Condition feature
R2: 0.605
##### Model #3
Dropping multicollinear feature: sqft_living
R2: 0.467
##### Model #4
Using significant features: sqft_living, grade, bathrooms
R2: 0.485
##### Model #5
Using relevant features and Onehotencoding on Condition feature
R2: 0.609
##### Model #6
Final Model: all of the above
R2: 0.871

## Evaluation
* The final model's predictiability increased to 0.871.
* The mean squared error represents for an average house, this algorithm will be off by about 104,012 dollars.
* According to our model, the price of an average house will go up by 16,594 dollars by one increase in bathrooms
* Investigate Linearity: Pass
* Investigate Normality - QQ Plot: Fail
* Investigate Multicollinearity: Pass, except for condition
* Investigate Homoscedasticity: Fail

## Conclusion

Together, square footage, grade and bathrooms are the best predictors of a house's price in King County. Homeowners who are interested in selling their homes at a higher price should focus on expanding square footage and improving the quality of construction. When expanding square footage, homeowners should consider building additional bathrooms, as this analysis suggests that number of bathrooms is positively related to price.

The model does have some limitations: given that some of the variables needed to be log-transformed to satisfy regression assumptions, any new data used with the model would have to undergo similar preprocessing. Additionally, given regional differences in housing prices, the model's applicability to data from other counties may be limited. Given that outliers were removed, the model may also not accurately predict extreme values.

## Recommendations

Our recommendations are as follows:

* increase square-footage of living space
* attain the highest possible building grade
* increase number of bathrooms

By following the above recommendations, a homeowner in King County can increase their chances of selling higher-priced homes.

## For More Information

For any additional questions, please contact:
* Kyunghwan William Kim at khwilliamkim@outlook.com

## Repository Structure

├── README.md                        <- The top-level README for reviewers of this project
├── King_County_Housing...ipynb      <- Jupyter notebook.
├── house_slides.pdf                 <- PDF version of project presentation
├── house_notebook.pdf               <- PDF version of Jupyter notebooks
├── data                             <- Both sourced externally and generated from code
└── images                           <- Both sourced externally and generated from code