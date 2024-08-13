# ml-project-1
ML project to satisfy course objectives, based on material in 
Udemy course [Machine Learning A-Z](https://www.superdatascience.com/pages/machine-learning).

## Problem Statement and Objective
Use machine learning to create a model that predicts which passengers survived the Titanic shipwreck.
This is a binary classification problem.   Data is as follows:

Label    | Meaning | Values
====
PassengerID | sequential     | irrelevant for training
Survival    |	Survival     |	0 = No, 1 = Yes
Pclass	    | Ticket class	 | 1 = 1st, 2 = 2nd, 3 = 3rd; proxy for social status
Name        | Last, Title First Middle | quoted string; title can give marital status for women, names can give hints to ethnicity
Sex	        | Gender         | "male" or "female"
Age	        | Age in years	 | may be non-integer; may be blank (cannot assume 0 in that case - use average?)
SibSp	    | # of siblings / spouses aboard the Titanic | integer, may be zero
Parch	    | # of parents / children aboard the Titanic | integer, may be zero
Ticket	    | Ticket number	 | not too useful, unless we can parse
Fare	    | Passenger fare | may also reflect social status
Cabin	    | Cabin number	 | may be useful if we can parse into deck, etc; some have multiple cabins, or none listed
Embarked	| Port of Embarkation |	C = Cherbourg, Q = Queenstown, S = Southampton; may also reflect social status
====

## Methodology
Normalize data, do test/train split, then create and compare several different models,
using different approaches and with hyperparameter tuning.  Use cross-validation as well as
test-train split to evaluate results and select the best model.

Note that Kaggle data already has a test/train split.   However, there are no results given for the "test.csv" file
from Kaggle so we can only evaluate results by submitting the predicted results for this file to Kaggle.

## Results

## Discussion 

## Links
* [Challenge and Data - Project C](https://www.kaggle.com/competitions/titanic)
   - Titanic - Machine Learning from Disaster
   - Will Cukierski, Titanic - Machine Learning from Disaster, Kaggle, 2012
* [Solution Notebook](solution.ipynb)
