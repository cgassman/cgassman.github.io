---
layout: post
title: "GCP first steps"
date: 2017-10-31
---

Objective of this month is to make first steps on the Google Cloud Platform (GCP); setting up a GCP account, get familiarized with basic concepts of GCP such as its identity and access management or its machine learning capabilities as well as understand basic concepts on compute engine, storage and so forth. The official GCP documentation serves as the starting point.

After one month of experimentation the samples worked via cloud shell as well as via command line APIs (gcloud and gsutil), the samples are easily accessible and applicable. The usage of cloud ml engine was easy over the cloud shell, but brought certain difficulties regarding required components and their supported versions. The integration between cloud ml engine and tensorflow was not very intuitive to me. My self-drawn conclusion that existing models need to be re-written in tensorflow had kind of a 'sobering' effect on me. However, tensorflow seems to be a very powerful tool and the integration of cloud ml engine sounds promising. One of the following months will be dedicated to tensorflow and cloud ml engine. But this months first steps build the basis...  

## Getting Started with Google Cloud Machine Learning Engine  
- setting up a GCP account, create new project, activat and adjust billing, activat two APIs (compute engine, machine learning engine)   
- install Cloud SDK to get access to the GCP via the command line.  
- install virtual environment, containing python (2.7) and tensorflow (version 1.2) as they are supported by the current machine-learning engine version of GCP. tensorflow needed to be updated, as explained later.  

Followed instructions, as outlined in [Google Cloud Platform - Cloud Machine Learning Engine - GettingStarted](https://cloud.google.com/ml-engine/docs/how-tos/getting-started-training-prediction)

Next, a walkthrough of a Cloud ML Engine sample that uses census data for training and prediction: Validate the trainer locally, run it in the cloud in both single-instance and distributed mode, use hyperparameter tuning to improve the model, and use the model to get online and batch predictions.

### run walkthrough via Cloud Shell  
thanks to the environment's pre-installation the focus can be set on the two cloud APIs and their usage, as well as on the machine learning part.
  
- **gcloud ml-engine** (needed for training and prediction); user arguments first, followed by command line arguments, separated by "--/"  
- **gsutil** (needed to manage storage and the data used)  

### run walkthrough via MAC-OS
as the environment has to be set up this provides a good opportunity to improve and refresh command line skills. 

```
VAR_NAME=output assigns value output to variable VAR_NAME. E.g TRAIN=$(pwd)/data/adult.data.csv   
echo $VAR_NAME displays value stored in variable VAR_NAME    
touch ~/.bash_profile; open ~/.bash_profile opens content of PATH variable in an easily editable mode   
 . (single dot) refers to current directory   
 .. (two dots) refers to on directory above from current directory   
 ~/ (tilde) stands for the user's homedirectory   
 /. (forward slash dot) refers to the root directory   
python -V to get information on installed version of python - 2.7.14 (in the tutorial used)   
pip show tensorflow to get information on installed version of tensorflow - 1.3.0 (in the tutorial used. Instead of 1.2.0!)     

gcloud components update  to update gcloud sdk  
gcloud auth login  to connect to gcloud  
gcloud projects list  to list projects of respective account  
gcloud compute instances create my-test-instance --zone us-central1-a  to create a standard compute vm.  
```

The tensorflow dependency provided some difficulties first. Although the tensorflow example successfully ran in the local environment, the tensorflow import threw an exception (import tensorflow not found) when trying to run it on the cloud environment. The "import tensorflow not found" error could be fixed by using virtualenv 15.1.0 and tensorflow 1.3.0 (instead of 1.2.0 as mentioned in the example and specified in the requirements.txt).  


## HousePrice example (from Kaggle) run on GCP - with Cloud ML Engine
Attempt to re-write current model for the HousePrice example - using sklearn - in tensorflow to fit into the gcp ml-engine concepts. 

**intro to tensorflow** some key concepts

- tensorflow provides basic (low-level) components to define own machine learning algorithms, optimizers etc. whereas sklearn provides 'standard' algorithms including default optimizers etc.  
- tensorflow additionally provides some basic estimators which are a similar concept to the algorithms provided in sklearn.  
- tensorflow represents algorithms as directed graphs. nodes are the computations (e.g. add, sum) and edges are input and output values.   
- on top of tensorflow the api named keras enables the creation of deep learning networks with tensorflow in a quite intuitive way.   


**re-write current model in tensorflow**
The following two python modules are being used.  

**task.py** - Defines general input arguments, arguments expected to run the experiment, as well as arguments which will be propagated from the experiment to the model.  
input arguments are used for example to describe the paths to the train data etc.  
experiment arguments are for example number of train steps or export strategies of the model.  
model arguments depend on the underlying model.    

**model.py** - defines the model which will be trained. In this example a LinearRegressor will be used. The model.py also contains loading of train and test data, as well as feature- extraction, selection or conversion. Conversions might be scaling, normalization, text to value transformations, just to name a few. 

The task.py for the HousePrice example is called as described in the walkthrough above, adjusted to the required arguments and the new model. 

(link to code will be inserted here)

## HousePrice example (from Kaggle) run on GCP with datalab
using datalab to run notebooks  
 
```
gcloud auth login
gcloud projects list
gcloud config set <projectId>

gcloud components list

if datalab is not installed yet, install it:
gcloud components install datalab 

datalab create my-first-datalab

open datalab on localhost:8081 in the browser...do work, run notebooks using sklearn.

datalab delete my-first-datalab
```

## IAM concept in GCP
Roles summarize permissions (such as read, write) based on these permissions, roles can access resources (such as storage, servers)
Roles can be assigned to a service account (representing an application) or to a user (representing an end user)
API keys are encrypted strings which are needed to identify a project for billing purposes. E.g. if my application wants to use the Translation API from Google, this can be used via API keys. The key identifys my application as a consumer and allows consumer based billing. 

