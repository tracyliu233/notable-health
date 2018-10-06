# Notable Health

## Env

The ipython notebook runs on conda virtual env. 

## Data exploration

The problem is predict ICD category given A/P in the data set. Noticing that one sentence of A/P can have multiple ICD categories. So we can approach the modeling as a multlabel classficiation. For each ICD category we can build one classifier, when we predict the ICD category for a givne A/P, we should run all classifiers on this A/P and label it with any ICD category with probability larger than 0.5.


## Data processing and modeling

The notebook starts with a few basic data process methods. It transform all A/P into lower case, remove punctuation except '-'. Also use the first 3 char to create ICD category as prediction label. 

Then use sklearn tfidf method to process A/P to create feature set. 

The choose model is Logistic regression. Also since for each classifier, the data set is unbalanced with positive example way less than negative, we can use upsampling on training data. The metric choosed is ROC AUC score, preciscion and recall. Prececial-Recall ROC can also be used if we care way more on false positive than true negative. 


