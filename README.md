# Machine Learning (Mobile Plan Recommendation Model)

## Overview
This project tackles mobile subscriber behavior for Megaline using machine learning. Many subscribers are on legacy plans, and the company wants to recommend either the Smart or Ultra plan based on data from users already on those plans. The target is to achieve a classification accuracy of at least 0.75.

## Objectives
- Develop a machine learning model to classify subscribers into Smart or Ultra plans based on their behavior.
- Achieve a model accuracy of 0.75 or higher, validated using a test dataset.
- Investigate the performance of different machine learning models by changing hyperparameters.
- Sanity check the model.

## Data Description
The dataset contains monthly behavior information for individual subscribers who have already switched to the Smart or Ultra plans. The features included are:

- `calls`: Number of calls made by the subscriber.
- `minutes`: Total call duration in minutes.
- `messages`: Number of text messages sent.
- `mb_used`: Internet traffic used in megabytes (MB).
- `is_ultra`: Plan for the current month (1 for Ultra, 0 for Smart).

## Key Insights
- Optimal Decision Tree `max_depth` is 9, with 79.32% accuracy (`random_state = 123`); default was 72.47%.
- Random Forest with `n_estimators = 42` achieved the highest accuracy: 80.4% on validation, 79.94% on test (`random_state = 123`).
- Logistic Regression is faster but less accurate than Random Forest, outperforming only the default Decision Tree.
- Baseline accuracy (guessing Smart) is 69.35%, while the best model reaches 78.38% on test data, showing improvement.
- Data split (60% train, 20% validation, 20% test) preserved skewness; sanity check confirmed model reliability.


## Tools and Technologies
- Python 3.10.12 
- Pandas 2.2.0 for data manipulation
- Scikit-learn 1.4.0 for machine learning models and evaluation