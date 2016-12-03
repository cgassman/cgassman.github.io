---
layout: post
title: "PCA on original data"
date: 2016-09-13
---

In this blog I do a principal component analysis (PCA). The dataset is still the same, customer satisfaction from Kaggle, as described in the respective [dataset description](/blog/2016/08/23/dataset-description). 

This to find out, if the satisfied customers can be 'separated' from the unsatisfied customers. As already done in prior blogs, I will split the respective dataset into a train- and a valid- set. The PCA will then be done on the train set only. It is important to know that the data has to be scaled/normalized prior to use.

## Relevant Imports
![relevant imports](/assets/code-snippets/2016-09-13-pca-original-data/relevant-imports.png "relevant imports")

## Read, Split Data
![read split data](/assets/code-snippets/2016-09-13-pca-original-data/read-split-data.png "read split data")

## PCA
![var ratio](/assets/code-snippets/2016-09-13-pca-original-data/pca-variance-ratio.png "variance ratio")
![code pca](/assets/code-snippets/2016-09-13-pca-original-data/pca-plot-1.png "code pca")
![cum var ratio](/assets/code-snippets/2016-09-13-pca-original-data/pca-plot-2.png "cum var ratio")
![pca plot](/assets/code-snippets/2016-09-13-pca-original-data/pca-plot-3.png "pca plot")

Although we could say that the unsatisfied customers are mainly along the first principal components, there is no real or even explicit split visible between satisfied and unsatisfied customers. But nevertheless, I will try out, how a random forest will look like on the respective pca data and how it will score regarding AUC/ROC. These results can then be compared with my prior score of 0.69.
