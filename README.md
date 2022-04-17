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
  - ![naive_random_oversamp_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/naive_random_oversamp_accuracy.png)
  - ![naive_random_oversamp_class.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/naive_random_oversamp_class.png)


- SMOTE Oversampling, new instances are interpolated, that is for an instance from the minority class, a number of its closest neighbors are chosen.  Based on the values of these neighbors, new values are created.  
  - ![smote_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smote_accuracy.png)
  - ![smote_classification.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/smote_classification.png)

### Undersampling:

- ClusterCentroids Undersampling, the algorithm identifies clusters of the majority class, then generates synthetic data points, called centroids, that are representatives of the clusters.  The majority class is then undersampled down to the size of the minority class.  
  - ![clustercent_accuracy.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/clustercent_accuracy.png)
  - ![clustercent_class.png](https://github.com/GrahamNeal13/Credit_Risk_Analysis/blob/main/resources/clustercent_class.png)


