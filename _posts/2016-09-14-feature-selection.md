---
layout: post
title: "Feature Preparation and Selection"
date: 2016-09-14
---

This blog is about feature preparation and feature selection. 
In feature preparation I will imput missing values or replace 'special' values that serve as fillers. The number of features remains the same. 
In feature selection I will select features according to different criteria, such as for example zero variance or identical features etc. 

Both these steps of preparation and selection come with a certain caveat. The preparation and selection is done based on the information from the train dataset. This means that the same observations can also occur in the valid or the test dataset, but they don't have to. As a conclusion the exact same steps as evaluated in the train set have to be applied on the valid and test dataset. No matter if the same observations can be made there or not. 

# Relevant imports and read data
![alt text](/assets/code-snippets/2016-09-14-feature-selection/read.png "read data")

# Feature preparation
Based on a manual analysis on the dataset, the following attributes have kind of 'filler-values' which will be replaced with the respective 75%-percentile value. The 75%-percentile value can be found via the describe() function on the dataset.
![alt text](/assets/code-snippets/2016-09-14-feature-selection/prep.png "prep data")

# Feature selection
There are various approaches available for feature selection: filters, wrappers and embedded methods. Filters look at individual features, they are easy to calculate and scalable. However, filters don't take dependencies to the learning algorithm nor correlations to other features into consideration. Examples for filters are ChiSquare, VarianceThreshold. Wrappers find a subset of features that fits best to a respective learning algorithm. It is an exhaustive and timeconsuming search. Examples for wrappers are Forward Selection, Backward Selection, Simulated Annealing. Embedded methods are methods where a feature ranking is integrated in the learning algorithm and therefore have better computing times. Examples for embedded methods are Support Vector Machines, Random Forests. 

In this blog we select features using the zero variance approach as well as a remove identical features approach. 

![alt text](/assets/code-snippets/2016-09-14-feature-selection/select.png "select data")

# Transformation applied to valid dataset
As explained at the beginning of this blog. The feature preparation and selection happened based on the train dataset. But the exact same changes will now be applied to the valid dataset without questioning or analyzing it. However, in the evaluation and performance phase we should consider again if this kind of preparation and selection was useful or if we lost too much information and made the situation worse. 
![alt text](/assets/code-snippets/2016-09-14-feature-selection/transform.png "transform data")

# Write data
![alt text](/assets/code-snippets/2016-09-14-feature-selection/write.png "write data")