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

Hence maximal 292 features, better 97, best 73. 


## Stage 3 - Assumptions Multiple Regression
Pre-condition: missing values resolved and samples checked for outliers.

Assumptions which have to be checked:
- Linearity
- Normality
- Homoscedacity
- Independence of error terms


