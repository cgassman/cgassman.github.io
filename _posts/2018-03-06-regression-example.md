---
layout: post
title: "Regression Example"
date: 2018-03-06
---

[work in progress] When I started to try to solve my first machine-learning problems, I always struggled with questions like: what needs to be done first? where to start? is there a workflow I can and need to follow or is everything done on a individual case by case basis? If so, how do these cases differ and where can I find them? etc. etc. 

This blog is an attempt to follow a structured six-stage model-building approach, found in the book [Multivariate Data Analysis](https://goo.gl/images/9Upv5w).  
It is the goal to apply these six steps to one of the getting-started competitions from [kaggle](https://www.kaggle.com) and build up a certain structure how machine learning problems can be approached.
The competition I chose for this experiment is [House Prices - predict sales prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)

Before starting, the six steps are quickly summarized, based on my personal understanding:  
**Step 1 - Objectives**: define problem, decide on multivariate technique to be used  
**Step 2 - Design**: develop the analysis plan, verify sample size, check on allowed and required types of variables (metric vs non-metric)  
**Step 3 - Testing Assumptions**: examine missing data, examine outliers, evaluate assumptions (linearity, normality, homoscedascity, independence of errors) and apply transformations where required  
**Step 4 - Estimate model and assess overall fit**  
**Step 5 - Interpret the variate**  
**Step 6 - Validate the model**  

Especially step 3 to 6 will be underpinned with respective Jupyter notebooks.  
 

## Step 1 - Objectives
As described in the kaggle competition itself, the objective is to predict the final price of a home, based on 79 explanatory variables.  
In other terms, there needs a relationship of a dependence to be explained. In this dependence, one dependent variable (in a single relationship) needs to be predicted; namely the final price of a home. Furthermore, the type of measurement scale of this final price of a home is metric. According to the figure describing how to select a multivariate technique, two multivariate techniques seem to be appropriate for this purpose:  

- Multiple regression: a statistical technique to analyze the relationship between one dependent and several indepentend variables Y1 = X1 + X2 + X3 ... while all of these variables need to be metric  
- Conjoint analysis: a technique developed to understand how respondents develop preferences for any type of object Y1 = X1 + X2 + X3 ... while Y1 can be metric or non-metric and X1, X2, X3 etc. are nonmetric.    
    
I will start with the multiple regression approach first, as I'm more familiar with it.

------------------------------------------------------------------------------------------------------------------  

## Step 2 - Design  


------------------------------------------------------------------------------------------------------------------  

## Step 3 - Testing Assumptions  

------------------------------------------------------------------------------------------------------------------  

## Step 4 - Estimate model and assess overall fit

------------------------------------------------------------------------------------------------------------------  

## Step 5 - Interpret the variate

------------------------------------------------------------------------------------------------------------------  

## Step 6 - Validate the model