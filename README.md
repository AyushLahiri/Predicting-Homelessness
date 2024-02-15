# Predicting the Risk of Homelessness Among Individuals with Substance Abuse Disorders

## Problem Statement
This study aims to predict the risk of homelessness among individuals suffering from substance abuse disorders using supervised learning methods. By analyzing demographic, employment, substance abuse disorder, and mental health disorder information of patients at admission to substance abuse disorder treatment facilities, the study seeks to determine if it's possible to predict their risk of homelessness by the time their treatment ends. This research aims to addresses co-occurrence of substance abuse, mental health conditions, and homelessness, highlighting the need for objective assessments to aid in quicker, targeted interventions.

## Dataset
The study utilizes the Treatment Episode Data Set - Discharges (TEDS-D) from 2020, published by the Substance Abuse and Mental Health Services Administration. This dataset includes approximately 1.4 million unique cases, with data on 76 different patient characteristics, collected at both admission and discharge from publicly funded treatment facilities in all states except Idaho, Maryland, New Mexico, Oregon, Utah, and West Virginia.

## Output Labels
The output variable of interest is the "Living Arrangement at Discharge," with a specific focus on identifying homelessness at the time of discharge. The dataset's imbalance, with only 13% of cases being homeless at discharge, necessitates techniques such as synthetic minority oversampling and random undersampling for model development.

## Adversarial Case
The adversarial case for prediction involves individuals whose homelessness status changes during the course of their treatment. This study excludes living arrangement at admission as a predictor to focus on predicting risk based on health and socio-economic conditions, without trivializing the prediction task by using current housing status.

## Models Used
- Logistic Regression
- Random Forests
- Gradient Boosting (XGBoost)
- Stacked Classifier (Meta-model: Random Forest)

## Recall and Focus on False Negatives
The study places particular emphasis on recall and the importance of minimizing false negatives (predicting individuals who are at risk of homelessness as not being at risk) due to the significant impact of such errors. Random Forests and Stacked Classifiers demonstrated the highest performance, with a careful consideration given to models that achieved higher recall scores. The best recall score achieved is 67.2%

## Error Analysis
Errors primarily stemmed from cases with changes in homelessness status during treatment. Misclassifications indicate potential systemic differences not captured by the variables or the impact of exogenous shocks leading to changes in homelessness status. We exercise caution in recommending more data capture in terms of variables, hypothesizing that the true root cause may be uncovered through more qualitative research such as life trajectories of such persons.   

## Limitations
1. **Sample Representation**: The dataset may not fully represent how substance abuse and other conditions predict homelessness due to limitations such as missing data for six states and the dataset only including individuals who seek treatment at publicly funded facilities.
2. **Case-Level Data**: The dataset logs separate cases for each admission, which may affect the accuracy and bias of the model due to the inability to group multiple admissions of the same individual.


