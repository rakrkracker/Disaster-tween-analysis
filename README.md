# disaster-tweet-analysis
Exploratory data analysis and machine learning algorithm for disaster prediction from tweets

## Overview
An exploratory data analysis and implementation of a random forest and bidirectional LSTM (BiLSTM) based models to predict disasters from tweets
for a kaggle challenge.

## Kaggle competition
This project is in response to the kaggle Distaster Tweets competition https://www.kaggle.com/c/nlp-getting-started -
Twitter has become an important communication channel in times of emergency.
The ubiquitousness of smartphones enables people to announce an emergency they’re observing in real-time. Because of this, more agencies are interested in programatically monitoring Twitter (i.e. disaster relief organizations and news agencies).
In this competition, the challenged is to build a machine learning model that predicts which Tweets are about real disasters and which one’s aren’t.

## Dataset
The data was taken from 10,000 tweets that were cand classified as associated with disaster or not.
Is was created by the company figure-eight and originally shared on their [‘Data For Everyone’ website here.](https://appen.com/open-source-datasets/)


https://www.kaggle.com/c/nlp-getting-started.
The model was built using the tensorflow/keras libraries.
Multiple differences were found in the data, such as an decreased average number of characters and words for disasters,
a clear bias towards non-disasters while using emoticons, and more.
The random forest model reached an accuracy of nearly 80%, and the BiLSTM dnn reached an accuracy of just above 80%.
