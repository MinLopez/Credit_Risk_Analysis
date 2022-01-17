# Credit_Risk_Analysis

## Overview
Reviewing credit loan applications data provided by LendingClub using imbalanced-learn and scikit-leark libraries for resamling. Then applying machine learning to predict loan application approvals.Then I will provide a recommendation.

## Resampling
- RandomOverSampling (oversampling)
- SMOTE (oversampling)
- ClusterCentroids (undersampling)
- SMOTEENN (oversampling/undersampling)

## Using Machine Learning to predict risk.
- BalancedRandomForestClassifier
- EasyEnsembleClassifier

## Results

### Sampling
#### RandomOverSampling
![Resources/Random_Oversampling.png](Resources/Random_Oversampling.png) 
- **Balanced Accuracy** : The balanced accuracy is ~71.7 Percent.
- **Precision** : The precision for high_risk is 1 Percent which is very low.
- **Recall** : The recall rate for high_risk is 74 Percent.

#### SMOTE
![Resources/SMOTE_Oversampling.png](Resources/SMOTE_Oversampling.png) 
- **Balanced Accuracy** : The balanced accuracy is ~69.5 Percent.
- **Precision Scores** : The precision for high_risk is 1 Percent which is very low.
- **Recall Scores** : The recall rate for high_risk is 64 Percent.

#### ClusterCentroids
![Resources/Cluster_Undersampling.png](Resources/Cluster_Undersampling.png) 
- **Balanced Accuracy** : The balanced accuracy is ~69.5 Percent.
- **Precision Scores** :The precision for high_risk is 1 Percent which is very low.
- **Recall Scores** :The recall rate for high_risk is 75 Percent.

#### SMOTEENN
![Resources/SMOTEENN_OVER_UNDER.png](Resources/SMOTEENN_OVER_UNDER.png) 
- **Balanced Accuracy** : The balanced accuracy is ~75 Percent
- **Precision Scores** :The precision for high_risk is 2 Percent which is very low.
- **Recall Scores** :The recall rate for high_risk is 72 Percent.

### Machine Learning

#### BalancedRandomForestClassifier
![Resources/Random_Forest_ML.png](Resources/Random_Forest_ML.png) 
- **Balanced Accuracy** : The balanced accuracy is ~67.2 Percent.
- **Precision Scores** :The precision for high_risk is 73 Percent which is very high.
- **Recall Scores** :The recall rate for high_risk is 34 Percent.

#### EasyEnsembleClassifier
![Resources/AdaBoost_ML.png](Resources/AdaBoost_ML.png) 
- **Balanced Accuracy** : The balanced accuracy is ~94.2 Percent.
- **Precision Scores** :The precision for high_risk is 7 Percent which is very low.
- **Recall Scores** :The recall rate for high_risk is 91 Percent.

## Summary

### Sampling
| Sampling         	| Accuracy 	| Precision 	| Recall 	|
|------------------	|----------	|-----------	|--------	|
| Balanced         	| 71.7     	| 1         	| 74     	|
| SMOTE            	| 69.5     	| 1         	| 64     	|
| ClusterCentroids 	| 69.5     	| 1         	| 75     	|
| SMOTEENN         	| 75       	| 2         	| 72     	|

Between the various sampling techniques used, the highest precision was SMOTEENN which the highest accuracy at 75 and third highest recall at 72 which is only 3 less than the highest at 75 for ClusterCentroids. This precision is still very low. *A low precision is indicative of a large number of false positives*. SMOTE was the worst of the 4 sampling methods. SMOTE had an accuracy at less than 70 percent, a precision of 1m and recall of 64 which is 8 behind  the next highest recall percentage for SMOTEENN at 72. *A low recall is indicative of a large number of false negatives.*

### Machine Learning
| Machine Learning 	| Accuracy 	| Precision 	| Recall 	|
|------------------	|----------	|-----------	|--------	|
| Random Forest    	| 67.2     	| 73        	| 34     	|
| Easy Ensemble    	| 94.2     	| 7         	| 91     	|

Between the machine learning techniques,  Easy Ensemble had a high accuracy at 94.2 Percent and a high recall at 91 Percent but its' precision was very low at 7 percent.
Random Forect had somewhat high, but lower than all of the sampling techniques used, at 67.2 Percent, a prevision of 73 Percent which is significantly higher than Easy Ensemble, and a low recall rate of 34 Percent.

In the case of approving credit loans, it is important to not approve credit loans to high risk credit users. It is also important that the precision of whether a person is high risk or not because we could miss out on approving a loan application for someone who actually has a low risk.

The sampling models all have low precision which means there are a large number of false positives- meaning high risk credit users are not being identified and loans approved which is a huge risk.
Random Forect almost comes close but the recall is lower which does suggest there a lot of false negatives - meaning many people who are low risk are being rejected.
Easy Ensemble had a very low prevision rate- meaning high risk credit users are not being identified and loans approved which is a huge risk.

Based on the sampling conducted, non of these models should be used.
