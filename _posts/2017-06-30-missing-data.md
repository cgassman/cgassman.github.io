---
layout: post
title: "Missing data"
date: 2017-06-29
---

Missing data might occur due to various reasons and different remedies could be applied. To get a real-life example, I applied the four step process from the 'Multivariate Data Analysis' book on the House Prices getting started competition from Kaggle.

It is important to understand possible patterns of missing data. Are parts of the data missed systematically, if yes, what might be the reason for this? Systematically missed data could bias the future model. From a practical perspective, missing data reduces the sample data available for analysis (rows) or reduces the set of possible features (columns).

[Code to this blog](https://github.com/cgassman/data-science-projects/blob/master/HousePrices/src/missing_data.ipynb)

## Step 1: determine the type of missing data - Ignorable or not ignorable missing data. 

Ignorable means missing data are expected and part of the research design or is inherent to the techniques used. For instance only taking survey-answers from a sample of the population and not all people or a specific design of the data collection process such as skipping sections if not applicable, but also censored data is a type of missing data which is ignorable. Ignorable means that remedies are not needed.
 
Not ignorable can be grouped into two classes, known versus unknown missing data. Knwon are for instance errors in data entry, creating invalid codes, disclosure restrictions etc. Unknown is more difficult to identify. Most often it is related directly to the respondent of a survey, e.g. the refusal to respond to a certain questions, respondent has no opinion etc. In case of not ignorable missing data (in both cases, unknown as well as known) remedies might be applicable, if the missing data are found to be random, but the extent and impact of missing data has to be assessed first.

## Step 2: determine extent of missing data.
- overall percentage of missing data
- missing data per feature
- missing data per observation/sample. This has a direct impact on numbers of features that could be used for a model. 5observations : 1feature (min), 15:1 (good), 20:1 (best)

differentiate between cases  
A) <10% missing  
B) 10%-20% missing  
C) >20% missing  


## Step 3: diagnose randomness of missing data.
Differentiate between MAR and MCAR data.  
MAR - missing at random. Data might be missing randomly in one feature, but the missing values are depending on the value of another feature.  
MCAR - missing completely at random. Cases with missing data are indistinguishable from cases with complete data. Preferred, as a it allows for the widest range of potential remedies.  

One option - especially when the data set is small - is to visualize missing data in a "patchwork rug" symbolizing missing values with a 'M' and leaving the the rest empty. This way patterns of missing data might be visible.  

As the sample size and the number of variables increase, the need for empirical diagnostic tests increases. Analyse randomness between groups (e.g. compare features) and analyse randomness overall, compared to expectation of complete randomness. 


## Step 4: select imputation method for MCAR
based on the cases differentiated above.  

**numeric**   
 A) try direct imputing (e.g. average, mean etc.)  
 B) analyse randomness (MCAR - random / MAR - patterns visible)  
 C) delete or replace. Risk for bias quite high. Regression method in case of MCAR, model based in case of MAR, if really needed  

**non-numeric**  
A) create dummy variables  
B) and C) tendency to delete or replace either single observations or whole feature, as imputation might bias 






