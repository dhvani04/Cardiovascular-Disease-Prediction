# Cardiovascular Disease Prediction

## Inspiration

In the last couple of decades, we have immense technological advancements in medical sciences. With Biosensors it is becomes possible to gather data constantly about our bodies and track our health at all times. With such large amounts of data and a good understanding of how our body functions, it really excites me to see how data science in particular will revolutionize the medical space, the way we take care of our health today and medical diagnosis. 

I feel that it is not very far in the future when we will have machines assisting doctors and even surpassing them on many aspects of medical diagnosis allowing them to spend their time on addressing more complicated treatment rather than mundane diagnosis. Moreover, when people become aware of their health condition just when it starts to deteriorate, it would give them an opportunity to take the right actions before things get worst and irreversible. 

Thus for my capstone project I wanted to address one area of medicine – Cardio vascular Disease and see how best can we get in term of prediction from very basic medical information about a patient.  

## Introduction

Cardiovascular Disease is one of the leading causes of death and 31% of the people in the entire world die of cardiovascular diseases every year. About 50% of Non-communicable Diseases are Cardiovascular Diseases. Moreover, the annual cost of cardiovascular disease is about $200 Billion in the US alone. 

As quoted by Michael Phelps, “The first symptom of Cardiovascular Disease is often fatal”. 
From medical studies we know the leading causes of Heart Disease. My goal for this project is to built a classification model that can predict whether a patient has Cardiovascular Disease or not based on basic medical information. 

## Data Collection

Kaggle has a dataset with 70,000 instances with data about 11 features describing basic medical information about people and whether they are suffering from CVD. 

## Features

1.	Age 
2.	Height 
3.	Weight
4.	Gender 
5.	Systolic blood pressure 
6.	Diastolic blood pressure
7.	Cholesterol
8.	Glucose
9.	Smoking
10.	Alcohol intake
11.	Physical activity
12.	Presence or absence of cardiovascular disease 

## Modeling Method and Findings:

Data Cleaning and Basic EDA: 
This sectioned involved removing outliers for a few features. I also transformed a few features like age in day was converted to age in years. I also checked for the balance of my data and then looked at the basic distribution of my features. 
As the data was balance, I decided to have accuracy score and AUROC score as performance metric for my models. Initially I performed baseline modeling on normal and scaled features with a range of classification model -Logistic Regression, Random Forest, KNN, SVM, Decision Tree to name a few to get an idea of which the best performance. Most of the models gave a neck to neck score. Even after optimizing with hyperparameters there was marginal or not improvement in the performance metrics. 

Next, I started with feature engineering and added features like BMI, ratio of Systolic/Diastolic Blood pressures and multiplying various features to see if a cumulative effect of features results in better separation and classification. I repeated the above process of modeling and checked for performance metrics. However, we again saw only little improvement in our performance metrics. The models and hyperparameter tuning that did not give a competitive score were tried and then deleted from the notebook for reducing confusion and complexity. At this point I also checked for feature importance with changes in feature set. 

This was followed by feature reduction and we found that even removing of multiple features with only 4-5 features in the model gave us a simple model and did not compromise the performance metric. 

After a bunch of feature engineering, feature reduction and model comparison I found that Logistic Regression and Random Forest performs the best among most of the models. So I decided to proceed with only these for further analysis. 
I thought that probably, for an older aged person having multiple condition would increase the chances of suffering from a CVD when compared to a younger adult whose body is more forgiving. So I thought it would be worthwhile to segment the data according to age and then checking the model performance. 

After segmenting the data I applied Logistic Regression and RF for each subset. From the results we found an exact opposite trend of what we initially expected. I achieved the highest score for the younger adult when compared to the older one. On reflecting on that for a while, I realized that an older adult might get a CVD simply because the cardiac muscles might get weaker or any other factor related to age. So even if he does not have glucose or sugar or other features, we might still see CVD for that patient and our model might fail to give a better accuracy score. On the other hand, for a younger the only features that might lead to CVD could be such abnormal conditions or lifestyle habits. With different age groups we also saw different feature becoming important for modeling. 

From this study we might conclude that we probably need to further investigate about what features could more accurately predict CVD in old people. Also this also tells us that as we got higher performance metric scores for young age group, we can have the opportunity to reverse certain conditions and make lifestyle changes, given time for improvement. 

## Notebook Navigation

All the analysis is summarized into one notebook from start to end. The initial part is Data Cleaning followed by EDA which is followed by Modelling.