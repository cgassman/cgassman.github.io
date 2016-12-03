---
layout: post
title: "SVM classifier"
date: 2016-09-17
---

Beside a trivial random forest, I wanted to train a support vector machine on the same data set, as described in the [data description](/blog/2016/08/23/dataset-description)
and check on the confusion matrix, see if an improvement to prior attemts is possible. 

This is in work. Normalization of data is still missing, which is key to SVMs. Firstly, I aim to get it up and running. 

## Relevant Imports
![relevant imports](/assets/code-snippets/2016-09-17-svm/relevant-imports.png "relevant imports")

## Read, Split Data
![read split data](/assets/code-snippets/2016-09-17-svm/read-split-data.png "read split data")

## Train Model and Predict
![model train predict](/assets/code-snippets/2016-09-17-svm/model-train-predict.png "model train predict")

## Evaluate Performance
![evaluate performance](/assets/code-snippets/2016-09-17-svm/evaluate-performance.png "evaluate performance")