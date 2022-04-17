# Credit_Risk_Analysis
Module 17

## Overview:

Background -  "Using the credit card credit dataset from LendingClub, a peer-to-peer lending services company, you’ll oversample the data using the RandomOverSampler and SMOTE algorithms, and undersample the data using the ClusterCentroids algorithm. Then, you’ll use a combinatorial approach of over- and undersampling using the SMOTEENN algorithm. Next, you’ll compare two new machine learning models that reduce bias, BalancedRandomForestClassifier and EasyEnsembleClassifier, to predict credit risk. Once you’re done, you’ll evaluate the performance of these models and make a written recommendation on whether they should be used to predict credit risk."

## Results:

Using Precision, which is the percent of predictions that are correct, we can see which tests are accurate.  The Recall scores will tell us the percent of positive cases that were caught within the model.  The Accuracy score with be the percent of all the tests, both positive and negative, that were correctly predicted.  This will also be an indicator for models that may have the error of overfitting.  As will the F1 score which is the weighted mean of both precision and recall.  In all cases the closer to 1 the values are the closer to 100% the better, although with accuracy score it is a sign of overfitting. 
With these scores we can evaluate which model will give us the most accurate idea of which loans will be good investments and which will be defaulted on.  

![accuracy_chart.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/accuracy_chart.png)

Below are the models that were used with the credit card dataset from the LendingClub.  

### Oversampling:

- Naive Random Oversampling, instances of the minority class are randomly selected and added to the training set until the majority and the minority classes are balanced.  
- The overall accuracy rating is high so this does bode well for the random oversampling.  The precision rates for high and low risk show a 0.01 and 1.00 score which means that there is a high likelihood of overfitting in this model.  As the recall rates show a 0.61 and 0.68 this does a good job of predicting the high and low.  
  - ![naive_random_oversamp_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/naive_random_oversamp_accuracy.png)
  - ![naive_random_oversamp_class.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/naive_random_oversamp_class.png)

- SMOTE Oversampling, new instances are interpolated, that is for an instance from the minority class, a number of its closest neighbors are chosen.  Based on the values of these neighbors, new values are created.  
- Using SMOTE gives a accuracy rating of 0.62 which is lower than random sampling and again we see the precision and recall of the this model are close with high risk getting 0.60 and low risk getting 0.64.  The F1 score is also off as the high risk is 0.02 and low risk is 0.78.  
  - ![smote_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smote_accuracy.png)
  - ![smote_classification.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smote_classification.png)

### Undersampling:

- ClusterCentroids Undersampling, the algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representatives of the clusters.  The majority class is then undersampled down to the size of the minority class.  
- The precison scores show high risk at 0.01 and low risk is 1.00 while the recall is 0.60 and 0.64 relatively speaking.  The F1 scores are also quite skewed with high risk at 0.02 and low risk at 0.78.  The overall accuracy score of 0.62.  
  - ![clustercent_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/clustercent_accuracy.png)
  - ![clustercent_class.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/clustercent_class.png)

### Combination (over and under) Sampling:

- SMOTEENN, combines the SMOTE and the edited nearest neighbors algorithm.  This follows two steps-
    1. Oversample the minority class with SMOTE
    2. Clean the resulting data with an undersampling strategy.  If the two nearest neighbors of a data point belong to two different classes, that data point is dropped.  
- The accuracy score of the SMOTEENN is 0.62, the precision score is 0.60 for high risk and 0.64 for low risk.  The F1 score is 0.02 for high risk and 0.78 for low risk.  The recall for high risk is 0.60 and the low risk is 0.64.  
  - ![smoteennor_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smoteenn_accuracy.png)
  - ![smoteenn_class.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smoteenn_class.png)

### Ensemble Learners:

- Balanced Random Forest Classifier, takes parameters like n_estimators, will allow us to set the number of trees that will be created by the algorithm.  Generally, the higher number makes the predictions stronger and more stable, but can slow down the output becuase of the higher traingin time allocated.  
- The accuracy score is 0.91 while the precision score for high risk is 0.04 and the low risk is 1.00.  The recall score is 0.67 for high risk and low risk showed 0.91.  
  - ![balanced_random_forest_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/balanced_random_forest_accuracy.png)
  - ![balanced_random_forest_class_report.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/balanced_random_forest_class_report.png)

- Easy Ensemble Adaboost Classifier, 
  - ![eec_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/eec_accuracy.png)
  - ![eec_class_report.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/eec_class_report.png)



