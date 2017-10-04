---
layout: post
title: "GCP first steps"
date: 2017-10-31
---

Objective of this month is to make first steps on the Google Cloud Platform (GCP); setting up a GCP account, get familiarized with basic concepts of GCP such as its identity and access management or its machine learning capabilities as well as understand basic concepts on compute engine and storage and so forth. The official GCP documentation serves as my starting point.

# Getting Started with Google Cloud Machine Learning Engine
- setting up a GCP account, created a new project, activated and adjusted billing, activated two APIs (compute engine, machine learning engine)  
- installing Cloud SDK on my mac to get access to the GCP via the command line.
- installing virtual environment on my mac, containing python (2.7) and tensorflow (version 1.2) as they are supported by the current machine-learning engine version of GCP. 

All done along the [Google Cloud Platform - Cloud Machine Learning Engine - GettingStarted](https://cloud.google.com/ml-engine/docs/how-tos/getting-started-training-prediction)

Test environment setup by running a first tensorflow sample on my local machine.

In the following steps walkthrough a Cloud ML Engine sample that uses census data for training and prediction. Validate the trainer locally, run it in the cloud in both single-instance and distributed mode, use hyperparameter tuning to improve the model, and use the model to get online and batch predictions.

## run this walkthrough via Cloud Shell
thanks to the environment's pre-installation the focus can be set on the machine learning part. Especially the two cloud APIs 
- gcloud ml-engine (needed for training and prediction); user arguments first, followed by command line arguments, separated by "-- \"
- gsutil (needed to manage storage and the data used)


## run this walkthrough via MACOS
as the environment has to be set up this provides a good opportunity to improve and refresh command line skills ;-) Especially the tensorflow dependency provided some difficulties.  
Although the tensorflow example successfully ran in the virtual environment, the tensorflow import threw an exception.  

Remark: refresh of most used commands for later re-use
- VAR_NAME=output assigns value output to variable VAR_NAME. E.g TRAIN=$(pwd)/data/adult.data.csv 
- echo $VAR_NAME displays value stored in variable VAR_NAME
- touch ~/.bash_profile; open ~/.bash_profile opens content of PATH variable in an easily editable mode
- . (single dot) refers to current directory 
- .. (two dots) refers to on directory above from current directory
- ~ (tilde) stands for the homedirectory
- gcloud components update to update gcloud sdk
- python -V to get information on installed version of python
- pip show tensorflow to get information on installed version of tensorflow


# IAM concept in GCP
Roles summarize permissions (such as read, write) based on these permissions, roles can access resources (such as storage, servers)
Roles can be assigned to a service account (representing an application) or to a user (representing an end user)
API keys are encrypted strings which are needed to identify a project for billing purposes. E.g. if my application wants to use the Translation API from Google, this can be used via API keys. The key identifys my application as a consumer and allows consumer based billing. 

