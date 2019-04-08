# Purpose of the Repository

This repository contains the results of the Data Science Nanodegree Sparkify Capstone Project. Its’s purpose is to give the reviewers access to the code. More information can be found on a [Medium Blog Post](https://medium.com/@christophberns/apache-spark-for-big-data-analytics-53b99185bf51).

# Overview 

Many music streaming provides (e.g. Spotify) collect huge amounts of data by collecting how users interact with their services (e.g. at which time a user is listen to a certain song etc.). These data contain valuable information to improve the services of the streaming providers. But the amount of generated data quickly exceeds the memory capacities of most personal computers. To still have the possibility to analyze this data, tools like Spark are necessary. Spark processes data in a distributed manner and as a result, Spark can also analyze data which does not fit into the memory of a single machine. Therefore, we use Spark in this Project to analyze user event log data of a music streaming service. 


# Sparkify Project Overview

Sparkify is a fictional music provider just like Spotify. In the Project, we analyse event data of Sparkify users. The data is given in terms of an event log which records events such as to which songs users are listening, are they adding friends or are they downgrading from paid to a free account etc. We work only on a tiny subset (128MB) of the full dataset available (12GB) since the analysis is done locally. The goal is to predict customer churn. Spark is used for the analysis in order to be able to scale well once the data of Sparkify exceeds the capacities to be analyzed on a single machine.

# Problem Statement
From a business perspective, we want to understand the factors that can predict or indicate customers churn behavior. If one understands these factors, it is possible to take countermeasures to avoid that certain users do not use the services anymore. The strategy is to define feature - based on the users behavior given by the event log - which can be used in a predictive model which predicts the likelihood that a user will churn before that happens. 
From a technical perspective, the challenge is to train a predictive model (by using Machine Learning techniques, e.g. Logistic Regression) on huge amounts of data. That's why Spark comes into play.

# Solution Strategy
We will tackle the problem in two steps:
### Data Exploration
In this step, we will get a general understanding of the data, clean it (e.g. remove missing values) and engineer features.
### Modelling
In a second step, we will use - based on the results of step 1 - Machine Learning to train a predictive model which can predict customer churn. The metric which we try to optimize will be f1-score.
     

# Data
The data in provided in JSON format. It is not included in the Repository, since it exceeds the volume which can be uploaded to GitHub but the entire dataset can be found at the Udacity Amazone S3 Bucket: s3n://udacity-dsnd/_sparkify_/sparkify_event_data.json.

# Files of the Repository 
The Repository contains this README.md and a folder called [Notebooks](https://github.com/chrisk2b/Project-Sparkify/tree/master/Notebooks).
The Notebook folder contains:

 - A Jupyter Notebook called Sparkify.ipynb which contains the entire analysis, including cleaning, feature engineering, modeling and improvements
 - A html version of the Notebook called Sparkify.html

Furter, the root folder of the project contains a requirement.txt file, cf. the sections below.
 

# Packages
The following packages are necessary to run the notebook:

 - pyspark
 - numpy
 - pandas

# How to Use the Repository
All code is in the Notebook [Sparkify.ipynb](https://github.com/chrisk2b/Project-Sparkify/blob/master/Notebooks/Sparkify.ipynb). Make sure that all dependencies which are mentioned in the section Packages have been installed. There is a requirements.txt file in the Repository which contains all relevant dependencies. You can install all dependencies from that file using pip via the command:
*pip install -r requirements.txt* 


# Results
The Machine Learning interface of Spark is quite comparable to the one of scikit-learn. Hence, training of a model in Spark is straight forward. We started with a first set of features and two different models (Logistic Regression and Gradient Boosted Trees). 
This yields to a f-1 score of 68%. Afterwards, we engineered additional features and trained also a Random Forest Classifier. This yields to a f1-score of 70%.

# Improvements
Improvements to the above results could be possible by applying e.g. the following approaches:

 - Include more features e.g. gender
 - Try more models, e.g. Deep Learning models
 - Use Grid Search for hyperparameter tuning
 - Try to find an additional data source which could be helpful for the considered task




