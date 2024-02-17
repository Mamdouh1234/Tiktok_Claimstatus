# Tiktok_Claimstatus
A predictive model for classifying Tiktok claim status


## Overview 

The goal of this project was to create a predictive model that predicts claim status for tiktok videos.
We trained thrww models which are  NaiveBayes , RandomForest and XGBOOST.
The champion model was Random Forest with recall 0.997.

## Business Understanding 

TikTok users can report videos that they believe violate the platform's terms of service. Because there are millions of TikTok videos created and viewed every day, this means that many videos get reported—too many to be individually reviewed by a human moderator.

Analysis indicates that when authors do violate the terms of service, they're much more likely to be presenting a claim than an opinion. Therefore, it is useful to be able to determine which videos make claims and which videos are opinions.

TikTok wants to build a machine learning model to help identify claims and opinions. Videos that are labeled opinions will be less likely to go on to be reviewed by a human moderator. Videos that are labeled as claims will be further sorted by a downstream process to determine whether they should get prioritized for review. For example, perhaps videos that are classified as claims would then be ranked by how many times they were reported, then the top x% would be reviewed by a human each day.

A machine learning model would greatly assist in the effort to present human moderators with videos that are most likely to be in violation of TikTok's terms of service.

## Data Understanding

The data consisted of approximately 19382 rows and 12 features. The features included information on tiktok videos such as: 
 - video duration
 - verified status
 - video views
 - likes
 - comments
 - downloads
 - shares
 - and the target variable claim status.

## Modeling and Evaluation 

We trained three models which are:
 - NaiveBayes
 - RandomForest
 - XGBOOST

Cross Validation technique was applied , the dataset was splitted to 70% for training , 15% for validation and 15% for unseen testing data which will be used to evaluate our champion model.
   
considering accuracy measures , for each model , we output a confusion matrix and four accuracy measures , they are
 - Accuracy
 - Precision
 - Recall
 - F1 Score
   
In the given scenario, it's better for the model to predict false positives when it makes a mistake, and worse for it to predict false negatives. It's very important to identify videos that break the terms of service, even if that means some opinion videos are misclassified as claims. The worst case for an opinion misclassified as a claim is that the video goes to human review. The worst case for a claim that's misclassified as an opinion is that the video does not get reviewed and it violates the terms of service. A video that violates the terms of service would be considered posted from a "banned" author, as referenced in the data dictionary.

Because it's more important to minimize false negatives, the model evaluation metric will be **recall**.

The champion model was **RandomForest** with Recall 0.997 on the validation set.

The model Scored 0.997 on the unseen testing set.

## Conclusion

The model performed well on both the validation and test holdout data. Furthermore, both precision and F1 scores were consistently high. The model very successfully classified claims and opinions.

The model's most predictive features were all related to the user engagement levels associated with each video. It was classifying videos based on how many views, likes, shares, comments ,and downloads they received.
