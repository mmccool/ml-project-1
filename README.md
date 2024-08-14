# ml-project-1
ML project to satisfy course objectives, based on material in 
Udemy course [Machine Learning A-Z](https://www.superdatascience.com/pages/machine-learning).

## Problem Statement and Objective
Use machine learning to create a model that predicts which passengers survived the Titanic shipwreck.
This is a binary classification problem.   

## Methodology
Normalize data, do test/train split, then create and compare several different models,
using several different approaches (SVC, XGBoost, Random Forest) with hyperparameter tuning via grid search where appropriate.  
Use cross-validation as well as
test-train split to evaluate results and select the best model.

Note that Kaggle data already has a test/train split.   However, there are no results given for the "test.csv" file
from Kaggle so we can only evaluate results by submitting the predicted results for this file to Kaggle.

## Results
The best models found were as follows.  Accuracy was computed against held-out test data.
Note that the grid-search models are actually slightly worse than the default models.
However, the grid search optimized based on cross-validation as opposed to the held-out test data.
Overall, the best results were obtained with an SVC model (with 82% accuracy) found through grid search
although the models were all quite close to each other, with roughly 80% accuracy.
| Model                     | Hyperparameters                     | Accuracy | 
| ------------------------- | ----------------------------------- | -------- |
| SVC default               | C = 1.0, gamma=scale, kernel=rbf    | 0.799    |
| SVC grid search           | C=0.45, degree=3, kernel=poly       | 0.821    |
| XGBoost                   | defaults                            | 0.804    |
| Random Forest             | criterion=entropy, n_estimators=10  | 0.782    |
| Random Forest grid search | criterion=entropy, n_estimators=435 | 0.799    |
| ------------------------- | ----------------------------------- | -------- |

## Discussion 
We did not use all the available data, for example, the cabins indicated location and most 
importantly the deck which may have been a factor in survival rate.  However, this information had
many gaps and it was not clear how to imput missing values.  Some of the other missing 
values in the data were odd, for example we found some passengers with missing ages but a 
quick Google search was able to discover the missing information.  We elected not to draw in more
data from outside sources to keep comparisons fair, and instead imputed missing values using average
values.  We also elected to not try to infer
ethnicity from names although that might also be possible.   We did not find a way to parse
the ticket field which at any rate was inconsistently formatted.

One other thing we did not try was dimensionality reduction.  The input data has a fair number of
dimensions and this might confuse some of the models.   We also did not try neural networks as we
did not feel there was enough data to train such a model well.

However, we felt the results from the SVC model found through grid search, 82% accuracy, were
fairly reasonable.  We were going to compare with the Kaggle leaderboard but it seems ALL the results on the 
leaderboard were "perfect" (score of 1.0) which was suspicious (who survived the Titanic is public 
knowledge, so submitters could have cheated by looking them up, and probably did) so we did not bother.

## Links
* [Challenge and Data - Project C](https://www.kaggle.com/competitions/titanic)
   - Titanic - Machine Learning from Disaster
   - Will Cukierski, Titanic - Machine Learning from Disaster, Kaggle, 2012
* [Solution Notebook](solution.ipynb)
