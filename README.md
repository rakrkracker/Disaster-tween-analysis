# disaster-tweet-analysis
Exploratory data analysis and machine learning modeling of disaster prediction from tweets

## Overview
An exploratory data analysis and implementation of a random forest and bidirectional LSTM (BiLSTM) based models to predict disasters from tweets
for the kaggle challenge https://www.kaggle.com/c/nlp-getting-started.
The model was built using the tensorflow/keras libraries.
Multiple differences were found in the data, such as an decreased average number of characters and words for disasters,
a clear bias towards non-disasters while using emoticons, and more.
The random forest model reached an accuracy of nearly 80%, and the BiLSTM dnn reached an accuracy of just above 80%.
