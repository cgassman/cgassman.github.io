---
layout: post
title: "Data preparation"
date: 2017-06-27
---

While doing data exploration on a new data-set, there is always a certain risk to get lost or at least distracted as soon as the data-set contains more than a few attributes. 
Either I went down a rabbit whole and lost oversight or I was browsing through the data on a very high-level and forgot about specialties in individual features.  
Therefore, I tried to find a way to keep track on newly gained insights in a structured way:

- Verify if there is a target variable to be predicted<br/>
- Describe the problem that has to be solved. E.g. binary classification, multi label classification, multi class classification, regression<br/>
- Understand the business domain and do some research (online, literature etc.) to get a better understanding<br/>
- Analyze if there is a train and a test data set and have a look at their shape<br/>
- Print for example an excel sheet with information I want to collect about individual attributes. The following code snippet outlines the structure of such a file, which will then be used while exporing the data step by step.<br/>

![alt text](/assets/prep_data.png "data preparation")

**AttributeName** - attribute's name used in the train-/test-data-set<br/>
**DataType** - attributes's datatype used to store the data e.g. int64, float64, object<br/>
**VarType** - attribute's type such as metric (ratio, interval) allowing arithmetic operations or non-metric/categorical (ordinal/ranking, nominal) variables<br/>
**MissingData** - how many values are missing in percentage of the respective attribute<br/>
**Outliers** - placeholder to add any insights regarding outliers<br/>
**Normality, Homoscedascity, Linearity, Independent Errors** - placeholders for the four underlying assumptions that should be analyzed especially for linera regression problems<br/>
**Expectation** - what is my initial expectation of the attribute's importance<br/>
**Conclusion** - what is the concluded importance of an attribute, based on the analysis<br/>
**ExampleValues** - examples of values that might be stored in this attribute<br/>
**Comments** - placeholder to add comments based on the analysis done<br/>

Additionally, literature research about the respective problem. Finding out, what additional information might be relevant or useful to model the respective problem. 




