# disaster-tweet-analysis
Exploratory data analysis and machine learning algorithm for disaster prediction from tweets

## Overview
An exploratory data analysis and implementation of a random forest and bidirectional LSTM (BiLSTM) based models to predict disasters from tweets
for a kaggle challenge.

## Libraries used
* TensorFlow
* Keras
* scikit-learn
* Numpy
* Pandas
* matplotlib
* seaborn
* random
* re
* NLTK
* gensim

## Kaggle competition
This project is in response to the kaggle Distaster Tweets competition https://www.kaggle.com/c/nlp-getting-started -
Twitter has become an important communication channel in times of emergency.
The ubiquitousness of smartphones enables people to announce an emergency they’re observing in real-time. Because of this, more agencies are interested in programatically monitoring Twitter (i.e. disaster relief organizations and news agencies).
In this competition, the challenged is to build a machine learning model that predicts which Tweets are about real disasters and which one’s aren’t.

## Dataset
The data was taken from 10,000 tweets that were cand classified as associated with disaster or not.
Is was created by the company figure-eight and originally shared on their [‘Data For Everyone’ website here.](https://appen.com/open-source-datasets/)

## Data Exploration
For this analysis, only the text of the tweets was used.
For uniformity, the text was lower-cased and lemmatized. In order to approach strings that are not words, a token was used for the most common categories: urls (http and https), hashtags (#), ats (@) and emoticons (:-)). All other non-lettered words and stop words were removed.
In addition, low frequency words (less than 10 in the entire dataset) were removed.
An average length analysis shows that disaster tweets tend to be shorter - less words, less characters and smaller word length.<br/>
![length analysis](https://github.com/rakrkracker/disaster-tweet-analysis/blob/master/images/analysis1.png)

A token frequency analysis shows that disaster tweets tend to have less "special" words (links, hashtags, emoticons, ect.)<br/>
![frequency analysis](https://github.com/rakrkracker/disaster-tweet-analysis/blob/master/images/analysis2.png)

A token distribution analysis shows that nearly 70% of tweets with locations are not disaster related. It also shows that more than 80% of tweets with emoticons are not disaster related. The rest of the special words are evenly distributed.<br/>
![distribution analysis](https://github.com/rakrkracker/disaster-tweet-analysis/blob/master/images/analysis3.png)

## Data preperation
The data was put through an embedding process based on the Word2vec algorithm. It was then split into training / validation sets with a ratio of 0.8 (6,090 training and 1,523 validation).

## Random Forest model
The data was fet into a random forest classifier. It reached a validation accuracy of 78.46%.

## BiLSTM model
This model uses a single layer of budirectional LSTM units, followed by global average pooling of the sequence and a dense classification head. Batch normalization and dropout layers were added throughout for stability.<br/>
![model architecture](https://github.com/rakrkracker/disaster-tweet-analysis/blob/master/images/rnn_model.png)

## Training
The model was trained in batches of size 64 and for a maximum of 100 epochs (a callback was added to stop training if nothing new was learned for multiple epochs). The training stopped after 39 epochs. The model reached an overall accuracy of about 80.6% (validation) and 80.4% (training), which indicated a good fit, without under- or overfitting. With an overall accuracy of 80.4%, this model shows improvement over the random forest one.<br/>
![learning curves](https://github.com/rakrkracker/disaster-tweet-analysis/blob/master/images/learning%20curves.png)
