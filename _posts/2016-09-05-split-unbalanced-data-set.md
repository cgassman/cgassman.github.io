---
layout: post
title: "Split an unbalanced dataset into a train- and valid- set"
date: 2016-09-05
---

The original train- set from Kaggle consists of more than 70'000 records, as described in the respective [data description blog](/blog/2016/08/23/dataset-description). In my opinion, this amount of data gives the opportunity to split this train- set into a train- and valid- set. I did this split with a ratio of 80% to 20%. There is always the question if you don't lose to much train- data if you set 20% aside, used for performance evaluation only. 

In my first approaches I didn't do any cross validation on the remaining 80% train- data. But it might be interesting to see how the algorithms perform with and without cross validation on the 80% train- data, or even with cross validation on the complete original train- set. But this will be analyzed in a separat future blog. 

However, in this blog I proceed with an explicit data split of 80/20 on the original train- set, without cross-validation, as you can see in the following code snippet. 

To keep the balance of satisfied vs. unsatisfied customers in the train- and valid- set, I used a [_StratfiedShuffleSplit_](http://scikit-learn.org/dev/modules/generated/sklearn.model_selection.StratifiedShuffleSplit.html). The resulting train set consists of 60816 records (80%), whereas the valid set contains 15204 records (20%). 

![split data](/assets/code-snippets/2016-09-05-split-unbalanced-data-set/datasplit.png "split data")

Thanks to the [_StratfiedShuffleSplit_](http://scikit-learn.org/dev/modules/generated/sklearn.model_selection.StratifiedShuffleSplit.html) the ratio of satisfied vs. unsatisfied customers remained the same in the train and in the valid set and also consistent to the original data set. 96% satisfied (=0) and 4% unsatisfied (=1) customers. 

![perc data](/assets/code-snippets/2016-09-05-split-unbalanced-data-set/percdatasplit.png "perc data")

I write all four parts into four different files. The valid set will only be used for performance evaluation, as you will see in the upcoming blogs. 

![write data](/assets/code-snippets/2016-09-05-split-unbalanced-data-set/write.png "write data")

Now I'm ready to train my first algorithms on the train-set. The valid-set will only be used to evaluate the performance of future trained models.  

