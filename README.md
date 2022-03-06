# Churn Prediction on User Log Data with Spark
## Project Overview

Sparkify is a music streaming service like Spotify. In this project, we try to find out insights from Sparkify's user log data and do churn prediction.

## Files
Sparkify.ipynb contains every step from data analysis, data wrangling, to model building/training/evaluation.

## Datasets and features

the user log data contains infomation about users, artists, and the current actions of users. Actions such as "NextSong", "Thump Up", "Thump Down", "Error", "Cancel", "Downgrade" are of special interests for our usecase. Therefore, we come up following statistics as the features for the machine learning model.
1. ever downgrad
2. number of songs played all time
3. number of thumbs up all time
4. number of thumbs down all time
5. number of errors all time
6. number of songs played in last week
7. number of thumbs down in last week/ number of songs played in last week
8. number of thumbs up in last week/ number of songs played in last week
9. number of errors in last week/ number of songs played in last week
10. last login time

### Balancing data
in the sample dataset, around 20% users churned. The dataset is unbalanced, therefore weights are added to train the binary classification models.

## Models and Framework
Spark is used to deal with the large amount of data, although we only use a subset of the total dataset.

Pyspark is the only package required.

I select Logistic Regresssion and Decision Tree as the candidate models. By comparing the f1 score, the Logistic regression performs better.