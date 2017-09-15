---
layout: post
title: "linear regression"
date: 2017-09-30
---

This blog summarizes a structured approach on the SalePrices example taken from Kaggle. The approach is taken from the book "Multivariate Data Analysis" chapter 4 - multiple regression analysis.

## Stage 1 - Research Problem
The House Prices data set is taken from Kaggle. It is a 'getting started' competition. The objective is to predict SalePrices. The interest is on a statistical relationship (not a functional). Statistical means it is an average value and a random component is part of it. 

The focus is on *predicting* the SalePrice (maximize overall predictive power of the independent variables). The explanation of the regression coefficients is secondary (magnitude, sign, and statistical significance of the regression coefficient for each independent variable).

The prediction gets more accurate the more variables are added. However, the interpretation and generalization is easier the fewer variables are used in the model. When in doubt, include irrelevant variables - this only confuses interpretation, instead of biasing all regression estimates. 


## Stage 2 - Research Design Issues & Creating Additional Variables
Given the sample size of about 1460 samples the adequate number of variables have to be found for statistical power on the one hand and generalizability on the other. 

A categorical variable with k categories will be transformed into k-1 dummy variables. 

To achieve a well generalized model, the degree of freedom (DF) should be as large as possible (DF = sample size - number of estimated parameters). A 5:1 ratio (samplesize:params) is a minimum. Better 15:1 even better would be 20:1. 

Hence 
- maximal 292 features to achieve a certain degree of generalization
- better 97
- best 73 features to achieve a high probability of a good generalization level


## Stage 3 - Assumptions Multiple Regression

Pre-condition: [missing values](https://cgassman.github.io/blog/2017/06/29/missing-data) resolved and samples checked for [outliers](https://cgassman.github.io/blog/2017/08/31/outliers).

Assumptions which have to be checked in a first instance for numeric variables:
- Linearity
- Normality
- Homoscedacity
- Independence of error terms

check these assumptions for 
- the target variable itself (univariate)
- for the features themselves (univariate)
- for the features against the target variable (bivariate)
- finally for the variate (predictions) itself (univariate)

in a second instance, non-numeric variables can be analyzed in a similar way, for instance if a quality increases while the target variable increases etc. 
So if for example quality is measured in high, medium, low, do we see a pattern that if quality is high, also sale price is high etc. 