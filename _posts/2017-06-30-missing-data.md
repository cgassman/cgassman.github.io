---
layout: post
title: "Missing data"
date: 2017-06-29
---

Missing data might occur due to various reasons and different remedies could be applied. To get a real-life example, I applied the four step process from the 'Multivariate Data Analysis' book on the House Prices getting started competition from Kaggle.

It is important to understand possible patterns of missing data. Are parts of the data missed systematically, if yes, what might be the reason for this? Systematically missed data could bias the future model. From a practical perspective, missing data reduces the sample data available for analysis (rows) or reduces the set of possible features (columns).

[Code to this blog](https://github.com/cgassman/data-science-projects/blob/master/HousePrices/src/missing_data.ipynb)

## Step 1: determine the type of missing data - Ignorable or not ignorable missing data. 

Ignorable means missing data are expected and part of the research design or is inherent to the techniques used. For instance only taking survey-answers from a sample of the population and not all people, specific design of the data collection process, censored data etc. Remedies are not needed.
 
Not ignorable can be grouped into two classes, known versus unknown. Knwon are for instance errors in data entry, creating invalid codes, disclosure restrictions. Unknown is more difficult to identify. An example is the refusal to respond to certain questions, no opinion etc. Remedies might be applicable, if the missing data are found to be random.  

## Step 2: determine extent of missing data.
- overall percentage of missing data
- missing data per feature
- missing data per observation/sample. This has a direct impact on numbers of features that could be used for a model. 5observations : 1feature (min), 15:1 (good), 20:1 (best)

differentiate between cases  
A) <10% missing  
B) 10%-20% missing  
C) >20% missing  

To visualize missing data it might be useful to print a "patchwork rug" symbolizing missing values with a 'M' and leaving the the rest empty. This way patterns of missing data might be visible.  

## Step 3: diagnose randomness of missing data.



## Step 4: select imputation method
based on the cases differentiated above.  

**numeric**   
 A) try direct imputing (e.g. average, mean etc.)  
 B) analyse randomness (MCAR - random / MAR - patterns visible)  
 C) delete or replace. Risk for bias quite high. Regression method in case of MCAR, model based in case of MAR, if really needed  

**non-numeric**  
A) create dummy variables  
B) and C) tendency to delete or replace either single observations or whole feature






