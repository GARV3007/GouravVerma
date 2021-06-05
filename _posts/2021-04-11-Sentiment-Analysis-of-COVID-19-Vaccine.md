---
title: "Sentiment Analysis of COVID-19 Vaccine Tweets"
header:
  teaser: "assets/images/Sentiment-Analysis-Tw.png"
categories:
  - NLP
  - Machine Learning
  - Classification
tags:
  - Sentiment Analysis
  - LTSM
  - Bi-LSTM
  - 1D-CNN
  - COVID-19
  - Vaccine
  - Tweets

author_profile: true
---

{% capture fig_img %}
![Foo]({{ '/assets/images/Sentiment-Analysis-Tw.png' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }}

### Abstract
In this research, we performed sentiment analysis of COVID-19 vaccine tweets using supervised machine learning approach. Social media is extensively used as a common platform to spread news and opinions. Identification of opinions towards COVID-19 vaccines would allow evidence-based decision making for better counsel and distribution of vaccines. Using social networking site Twitter, tweets from across the world were extracted for a set of vaccine related keywords. These tweets were gathered from Nov-2020 to March-2021. A random sample of the whole dataset was cleaned by applying text pre-processing techniques. As tweets contain emoticons and short words, it is difficult to correctly recognize the context of the tweets. To overcome this issue dataset with existing sentiment labels was used to train the models. Tweet sentiments are classified into three categories Positive, Negative, and Neutral. The sentiments were annotated and supervised learning methods RNNs (Single LSTM and Bidirectional LSTM) and 1D CNN were applied to train the tweet training dataset. Performance of the classifiers is evaluated on accuracy. With Bidirectional LSTM model, we achieved 74% accuracy, and it was used to implement on the COVID-19 vaccine tweets dataset.
<br />

### Problem Statement
The year 2020 was full of COVID-19 spread across the world, multiple lockdowns, and burnout of essential workers. So far, 2021 has been focused on vaccine distribution. March 11, 2021 was the first anniversary since WHO declared COVID-19 as a global pandemic. As everyone wanted to go back to normal life, people were closely monitoring vaccine developments. During the lockdown COVID-19 news spread was enormously amplified in social networking platforms. Being a highly popular social platform, Twitter provides a large scale of text data for various research such as sentiment analysis. Involvement of individual views and biasness in the vast fragment of these news, is giving growth to (un)intended fake information, negativity, and ambiguity in the human society. These circumstances are gathering attention of researchers to carry out computational study for forming a complete representation. This research is focused on sentiment analysis of COVID-19 vaccine tweets using supervised machine learning approach. Due to the overflowing COVID-19 news and speedy development of a vaccine, people rationally have many questions on vaccines. Some of them are:
 - Do the mRNA vaccines change your DNA? 
 - Did the vaccine clinical trials skip steps to be completed faster? 
 - Can the vaccine give you COVID-19? 
 - Will we need new vaccines if the virus continues to mutate?
Such questions and limited reliable answers lead to confusion and doubts overtaking the vaccine. As per Panacea lab every day, there are about 4 million tweets a day related to COVID-19. This study utilizes tweets to understand people’s sentiments. It will help understand the difference in sentiments for different vaccines and the change in sentiments over time.
<br />

### Data
For this project, we used tweets about the COVID-19 vaccines distributed in the entire world. Tweets are collected using the tweepy Python package to search Twitter API for the keywords relevant to COVID-19 vaccines. The tweets are about Pfizer/BioNTech, Sinopharm, Sinovac (both Chinese-produced vaccines), Moderna, Oxford/Astrazeneca, Covaxin, and Sputnik V vaccines. 
The tweets dataset contains below columns –
•	Id: 		Total 60.3k values
•	User_name: 	60.3k values ,32.6 unique values
•	User_location: 	13.8k missing values
•	User_description: 4158 missing values
•	User_created: 	user creation date.
•	User_followers:	follower count of user
•	User_friends: 	friends count of user.
•	User_favourites
•	User_verified: 	True-6421, False-53.9k
•	Date: 		Tweet date
•	Text: 		Tweet text, 60.3k tweets
•	Hashtags: 	hashtags
•	Source: 		web-31%, phone-29%
•	Retweets: 	retweet count
<br />

### Methodology
This section provides an overview of the methodology applied in this research. The complete pipeline is shown in the Figure 1. Broadly the experiment is carried out in three different phases including (i) Data preparation phase, (ii) Modelling phase, and (iii) Implementation phase. In the first step we scrapped the tweets related to COVID-19 vaccines from Twitter, cleaned, annotated, and randomly selected for implementation. The second phase involves building a sentiment classifier model using a training dataset. In the final implementation phase the best model was applied to the COVID-19 vaccine tweet dataset and outcome was used analyse the sentiment trends.

Tweets texts are informal language forms. In tweets there could be multiple meanings of the same word and sentences might not be grammatically correct. Hence, traditional rule-based models such as word2vec, Tfidf, and BoW cause week performance for sentiment analysis of tweet texts. For the project, we decided to use LSTM models, which is one of the best RNN models in NLP. RNN takes a word as an input instead of the entire sample. It enables RNN to work with sentences of variable lengths.
<br />

### Results
It’s been a long timeframe of sickness, sadness, hopelessness, and distress, but the rollout of COVID-19 vaccination globally has given rise to feelings of relaxation for so many. The information about vaccination, side effects, and efficiency is ongoing and circulating on social platforms. This project utilized the power of NLP on Twitter data to understand the sentiments of people over-vaccination. Python package NLTK was used for tokenization/detokenization. LSTM, Bi-LSTM, and 1D CNN models were trained and evaluated for accuracy. Highest accuracy of 72.7% was achieved by Bi-LSTM and it was used for implementation on COVID-19 vaccine tweets dataset. Trends of different sentiments were drawn using Tableau. We see higher number of negative tweets as compared to positive tweets. Moderna, Sinovac, Sputnik, and Johnson & Johnson show an increasing trend in negative sentiment. Pfizer seems to have a constant level of negative sentiment. USA has highest number of vaccinations done as of May 1st. As the 2nd wave of virus has hit India hard, it needs to ramp up its vaccination per hundred. For further analysis dataset with complete tweet text, if available, can be utilized.
<br />

### [Github Repository](https://github.com/GARV3007/COVID-19-vaccine-Tweets){: .btn .btn--primary .btn--small}
