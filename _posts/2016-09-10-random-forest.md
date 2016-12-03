---
layout: post
title: "Random forest and prediction accuracy in an unbalanced dataset"
date: 2016-09-10
---

This blog tells you the story of one of my first high-lights and enthusiastic moments, which was followed by a very "bring me down to earth again" moment only a few moments later. 

However, I'm still excited that I got my first (even though very simple) random forest model running and I learned that prediction accuracy has to be taken with a grain of salt, especially if you have an unbalanced dataset. 

Let's see why:       
I started with relevant imports, read in data, split data into a train- and valid- set, as already explained in one of my first blogs on data splits. All these steps I count to the data preparation step in my overall [machine learning model](/blog/2016/08/31/machine-learning-overview)

![relevant imports](/assets/code-snippets/2016-09-10-random-forest/relevant_imports.png "relevant imports")
![read split data](/assets/code-snippets/2016-09-10-random-forest/read_split_data.png "read split data")

As a next step on my machine learning overview, I train a first prediction model on my X_train and Y_train data. The valid-set (X_valid and Y_valid) will only be used to evaluate my model's performance. My first model will be trained on a very simple random forest. Very simple, as I only set one parameter. 
Right after the training, I did a first evaluation on the metric: prediction accuracy. In simple words I let the trained model predict, if a customer in the X_valid set is satisfied/unsatisfied, I then compared this prediction with the true value (Y_valid).    

## Train Model, Evaluate Performance     
![random forest](/assets/code-snippets/2016-09-10-random-forest/train-rf-pred-acc.png "model train random forest")

An amazing prediction score of 95.44%!!! So 95.44% of my predictions were correct by using this simple model. I thought that is great, but being sceptical on such a high score with my first trial ever on a problem that has been posted on Kaggle. I did some research...

... __using prediction accuracy, always have a look at the balance in your dataset__. So, how many 1s and 0s are in there? Checking this on the original dataset (and as shown in the [data split blog](/blog/2016/09/05/split-unbalanced-data-set) this is also valid for the train and the valid set).

![dataset balance](/assets/code-snippets/2016-09-10-random-forest/data-set-balance.png "model train random forest")

Well, this means: even if I had trained no prediction model at all, only had predicted 0 (=satisfied) per default, I would have had a prediction accuracy of 96%. Btw, this is even better than with my simple random forest. What an eye-opener - and in the first moment also disappointment!

I started to get information on metrics, when to use which, what do they mean etc. The confusion matrix is mentioned as one of the main indicators how a model performs. Additionally, on kaggle.com I found out that the metric being used for this competition was AUC/ROC. So I watched some YouTube videos on this, read articles and tried to apply this to my model. 

## Confusion Matrix
![confusion matrix](/assets/code-snippets/2016-09-10-random-forest/confusion-matrix.png "confusion matrix") 

Based on this confusion matrix:           
- true satisfied (0) and predicted as satisfied(0) = 14484 (TN - true negative)        
- true satisfied (0) and predicted as unsatisfied(1) = 118 (FP - false positive)         
- true unsatisfied (1) and predicted as satisfied (0) = 575 (FN - false negative)        
- true unsatisfied (1) and predicted as unsatisfied (1) = 27 (TP - true positive)         

Personally, I would say the FP are not nice, but in the worst case I have to approach a satisfied customer again to try to make im satisfied. What really hurts from my point of view are the FN: People that have been predicted as satisfied, but are actually unsatisfied!    

## AUC/ROC     
![auc roc](/assets/code-snippets/2016-09-10-random-forest/auc-roc.png "auc roc")

Is this good or bad? Well, I think that depends on the difficulty of the problem. But given some default guidelines, this is rather poor.    

auc values:    
* 0.9 - 1.0 = excellent      
* 0.8 - 0.9 = good       
* 0.7 - 0.8 = fair       
* 0.6 - 0.7 = poor        
* 0.5 - 0.6 = failed       

This can also be seen by the roc curve which is 'quite flat'. The optimal curve (e.g. an excellent classifier's roc curve) would hit the upper left corner. Compared with the leader board on Kaggle, much more should be possible (e.g. 0.84 public and 0.82 private). So let's see if I can improve this in one of my next blogs...

  
