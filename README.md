# ECS 171 Project Write Up | Team 9 | Titanic Survival Prediction

## Group Members :
#### Eric Young, David Zhang, Brian Lai, Alejandro Medina, Zhehao Fan, Ryan Buchner, Kevin He, Xuan Huang, Zunaira Ahmad, Jonathan Chesney

## How to Use
Must have access to Jupyter Notebook

Open CNB_DecisionTree.ipynb

For Windows/Linux :
 1. Ctrl + A [Select All Cells]
 2. Shift + Enter [Run all Selected Cells]

For Mac :
 1. ⌘ + A [Select All Cells]
 2. Shift + Enter [Run all Selected Cells]

## Pre-Processing Data
* Pre Processed data includes handing missing data like age. 
* Used one-hot-encoding on categorical attributes such as Pclass, gender, and location of embarkation. 
* Used MinMaxScaling for numerical attributes.

## Building Neural Network
* Split the data into training-test sets with the test size of 0.1. 
* Used MLPClassifier with the following parameters : solver = sgd, random_state = 42, activiation = logisitic, learning_rate = 0.05, hidden_layer_sizes = (15,1,0), max_iter = 1500.

## Training and Testing Model
* Fit our model and predicted on the test set results in a 68% accuracy with a .227 MSE. 
* Results found using accuracy_score and mean_squared_error

## Average Accuracy and Error using Cross Validation
* Cross Validating on our Neural Network model with cv = 10, scoring based on accuracy and neg_mean_squared_error. 
* Average accuracy is 79.8%, average MSE is 0.20.

## Fitting a Categorical Naive Bayes Model
* Extracted categorical attributes and encoded using OrdinalEncoder. 
* Split the training-test data into .8 : .2. 
* Results displayed in a classification_report.

## Fitting a Decision Tree Model
* Split training-test set into 0.8 : 0.2. 
* Built model using entropy as criterion and best splitter. 
* Results displayed in classification_report.

## Pre-Pruning Tree Model
* Set a dictionary with a list of maximum depth values. 
* Used GridSearchCV with 10 kfolds. Extracted model, fit training data, and results displayed in classification_report.

## BONUS : RF with Grid Hyperparameter Search
* Established n_estimators : (100,300,500,1000), criterion : (gini, entropy), min_samples_split : [2,11], min_samples_leaf : [1,9]. 
* Used GridSearchCV with 10 kfolds. 
