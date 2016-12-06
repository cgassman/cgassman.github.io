---
layout: post
title: "PCA on selected data incl. Random Forest"
date: 2016-09-15
---

In this blog I do a principal component analysis (PCA). The dataset is still the same, customer satisfaction from Kaggle, as described in the respective [dataset description](/blog/2016/08/23/dataset-description). 

This to find out, if the satisfied customers can be 'separated' from the unsatisfied customers. As already done in prior blogs, I will split the respective dataset into a train- and a valid- set. The PCA will then be done on the train set only. It is important to know that the data has to be scaled/normalized prior to use.

## Relevant Imports, read data, split data
![relevant imports](/assets/code-snippets/2016-09-15-pca-selected-data/relevant-imports.png "relevant imports")

## PCA
![code pca](/assets/code-snippets/2016-09-15-pca-selected-data/pca.png "code pca")
![pca plot](/assets/code-snippets/2016-09-15-pca-selected-data/pca-plot.png "pca plot")
![cum var ratio](/assets/code-snippets/2016-09-15-pca-selected-data/cum-var-ratio.png "cum var ratio")

Although we could say that the unsatisfied customers are mainly along the first principal components, there is no real or even explicit split visible between satisfied and unsatisfied customers. But nevertheless, I will try out, how a random forest will look like on the respective pca data and how it will score regarding AUC/ROC. These results can then be compared with my prior score of 0.69.

## Random Forest
![train rf](/assets/code-snippets/2016-09-15-pca-selected-data/train-rf.png "train rf")
![confusion matrix](/assets/code-snippets/2016-09-15-pca-selected-data/train-rf.png "confusion matrix")
![roc auc](/assets/code-snippets/2016-09-15-pca-selected-data/roc-auc.png "roc auc")
![roc auc plot](/assets/code-snippets/2016-09-15-pca-selected-data/roc-auc-plot.png "roc auc plot")