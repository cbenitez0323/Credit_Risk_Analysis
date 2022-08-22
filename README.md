# Credit_Risk_Analysis

## Overview of the analysis: 
Used credit card data in order to predict credit risk. Because of the unbalanced set, oversampling, undersampling and SMOTE techniques were used to account for the class imbalance. Then using the same data, implelment ensemble machine learning in order to reduce bias.

## Results: 
### naive random oversampling 
- Oversampled the data by using naive random oversampling algorithm. 
- The balanced accuracy score is about 0.65 which means that about 65 percent of testing set was predicted correctly using the model. 
- The confusion matrix shows that the model predcited 1003511 true negatives. 
- Then the imbalanced classification report shows that the precision of high risk credit is low which means there is a larger number of false positives. In this case that means that the model will correctly predict the moajoity of the high risk class but will incorrectly include some low risk accounts. 

<img width="668" alt="oversampling" src="https://user-images.githubusercontent.com/102255823/185984113-d2a070fa-7dd8-4a55-bc22-936f83d91489.png">

### SMOTE Oversampling
- Next, oversampled using SMOTE algorithm.
- The balanced accuracy score was about 0.66, which is slightly better than the previous oversampling technique. 
- The confusion matrix shows that the recall for the high risk class is high risk is high. This means that there is a low nummber of false positives. In this case a low number of incorrectly predicting a low rish when actually being a high risk account. 
- The 

<img width="669" alt="SMOTE oversampling" src="https://user-images.githubusercontent.com/102255823/185986431-adecc9e6-ab2e-4f3b-b76c-dffb2da31bb5.png">

### Cluster Centroids 
- Undersampled the data using the clustercentroids resampler which takes data points from the majority class and then generates cetroids that represent data point clusters in order to reduct the size of the majority class. 
- The balanced accuracy score is about 0.54 which is less than both the oversampling techniques used. 
- The confusion matrix showed that there were 31 incorrectly predicted low risk accounts that were actually high risk.
- The imbalanced classification report shows that for the high risk class, the model has high precision but low recall. Which means that the model will be able to correctly predict high risk account but will miss a few. 

<img width="667" alt="undersampling" src="https://user-images.githubusercontent.com/102255823/185988263-6008b98f-a639-4c5f-982d-d9f1931b7748.png">

### SMOTEENN algorithm 
-Performed a combination of undersampling and oversampling using the SMOTEEN algorithm that oversamples the minority class by using SMOTE and dropping points that overlap classes. 
- The balanced accuracy score is about 0.65 and therefore closer to the accuracy scores from oversampling. 
- The confusion matrix shows that the model missed about 28 high risk accunts that were predicted to be low risk. 
- The imbalanced classification report shows that the model has high recall and low precision in predicting high risk accounts. This means there are low number of incorrectly predicted a low risk account when its actually high risk. There is an imbalance of precision and recall as indictated by the low F1 score of 0.02.

<img width="665" alt="combo sampling" src="https://user-images.githubusercontent.com/102255823/185990327-5f8134b7-d4e2-4805-a5bf-839e089d8f80.png">

### Balanced Random Forest
- Used data to train a Balanced Random Forest Classifier.
- The balanced accuracy score was 0.74 which is high. 
- The confusion matrix showed that 30 of the predicted low risk were actually high risk.
- The precision was low and the accuracy was high for the the high risk prediction which lead to the low F1 score. 

<img width="665" alt="balanced randomforestclassifier" src="https://user-images.githubusercontent.com/102255823/185991356-10be1bde-a043-4b80-a7fe-8d50a1f9039b.png">

### Easy Ensemble 
- The easy ensemble had the highest balanced accuracy score at 0.92.
- The confusion matrix showed 7 accounts were predicted to be low rish but were actually high risk which is better than balanced random forest. 
- For predicting high risk accounts, the F1 score was 0.1 which is better than the previous model and therefore there is a better balance between the precision and recall of the model. 

<img width="661" alt="easyensembleclassifier" src="https://user-images.githubusercontent.com/102255823/185992140-39a17a69-d4a2-4ed6-9875-e1ab92775399.png">

## Summary: 
The models did fairly poor because they have a low F1 score that showed there was an imbalance between the precision and recall of the model. When it comes to predicting if an account is low or high credit risk, it is better to be able to correctly predict all the high risk accounts but to also inccorectly include low risk accounts in the classification. Therefore it is understandable why the models would have high recall. When looking at the features importance, 'total_rec_prncp' was the highest therefore it was the highest predictor in determining if an account was high risk. However, there were also many features that were very small predictors. It may imporve the model to be able to remove those features and see if the model improves. Most likely, other features would need to be tested to see if the model could be imporved. 
