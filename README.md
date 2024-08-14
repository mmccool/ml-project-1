# ml-project-1
ML project to satisfy course objectives, based on material in 
Udemy course [Machine Learning A-Z](https://www.superdatascience.com/pages/machine-learning).

## Problem Statement and Objective
Use machine learning to create a model that predicts which passengers survived the Titanic shipwreck.
This is a binary classification problem.   

## Methodology
Normalize data, do a stratified test/train split, then fit and compare several different models,
using several different approaches (SVC, XGBoost, Random Forest) with hyperparameter tuning via grid search where appropriate.
Use cross-validation as well as accuracy on held-out test data to evaluate results and select the best model.
See the [Solution Notebook](solution.ipynb) for details.

Note that Kaggle data already has a test/train split.   However, there are no results given for the "test.csv" file
from Kaggle so we can only evaluate results by submitting the predicted results for this file to Kaggle.

## Results
The best models found were as follows.  Final accuracy was computed against held-out test data.
The grid search optimized based on 5-fold cross-validation as opposed to the held-out test data.
Overall, the best results were obtained with an SVC model (with 82.1% accuracy) based on a degree-3
polynomial kernel found through grid search.
However, the models were all quite close to each other, within a few percent of 80% accuracy.
| Model                     | Hyperparameters                     | Accuracy | 
| ------------------------- | ----------------------------------- | -------- |
| SVC default               | C=1.0, gamma=scale, kernel=rbf      | 79.9%    |
| SVC grid search           | C=0.45, degree=3, kernel=poly       | 82.1%    |
| XGBoost                   | defaults                            | 80.4%    |
| Random Forest             | criterion=entropy, n_estimators=10  | 78.2%    |
| Random Forest grid search | criterion=entropy, n_estimators=435 | 79.9%    |

## Discussion 
Not all the available data was used; for example, the cabins indicated location and most
importantly the deck which may have been a factor in survival rate.  However, this information had
many gaps and it was not clear how to imput missing values.  Some of the other missing
values in the data were odd, for example some passengers had missing ages but a
quick Google search was able to discover the missing information.  I elected not to draw in more
data from outside sources to keep comparisons fair, and instead imputed missing values using average
values.  I also elected to not try to infer
ethnicity from names although that might also be possible.
I did not find a way to parse the ticket field which at any rate was inconsistently formatted.

One other thing I did not try was dimensionality reduction.  The input data has a fair number of
features and this might confuse some of the models. I also did not try neural networks as there
did not seem to be enough data to train such a model well.

However, I felt the results from the SVC model found through grid search, 82% accuracy, were
fairly reasonable.  I was going to compare with the Kaggle leaderboard but it seems ALL the results on the
leaderboard were "perfect" (score of 1.0) which was suspicious (who survived the Titanic is public
knowledge, so submitters could have cheated by looking them up, and probably did) so I did not bother.

## Links
* [Challenge and Data - Project C](https://www.kaggle.com/competitions/titanic)
   - Titanic - Machine Learning from Disaster
   - Will Cukierski, Titanic - Machine Learning from Disaster, Kaggle, 2012
* [Solution Notebook](solution.ipynb)
