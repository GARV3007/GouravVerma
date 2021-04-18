---
title: "Women Clothing Reviews"
header:
  teaser: "assets/images/Dresses.jpg"
categories:
  - Sentiment Analysis
  - Clustering
  - Prediction
  - Recommendation
tags:
  - K-Means
  - AFINN Lexicon
  - scikit-surpise
  - BaselineOnly
toc: true
---

{% capture fig_img %}
![Foo]({{ '/assets/images/Dresses.jpg' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }}

### Abstract
Most of the marketing companies are able to segment the customers in order to create personal, timely and pertinent content, but how many companies know how their audience feel before they spend their scrutinised marketing budgets trying to get them to spend more? People will forget what you said, people will forget what you did, but people will never forget how you made them feel –this statement holds extremely true in the world of retail as well. By analysing these sentiments accurately and analysing the things that upsets the customer, a retailer can focus more on what will make a difference. We can leverage machine learning technology as an opportunity to find it. In this project women-clothing review dataset from Kaggle is used which has many variables like age of the customer, clothing review text, ratings provided by customers, unique clothing ids, and department. To generate sentiment scores from the review text given by women on clothing items, the AFINN lexicon library was used. Later K-Mean clustering algorithm was applied to the sentiment score to generate customer segments based on their age. Review ratings by the customer and unique clothing item ids and age parameters from the dataset were used to build a recommendation model. Using the model an unknown user-rating can be identified, moreover, this model can be leveraged to recommend a clothing item to a woman based on her age. For building the recommendation model surprise package from the scikit group is used and post performing cross-validation BaselineOnly algorithm was chosen for the task. 

### Data Sources
Women’s Clothing E-Commerce dataset with customer review comments from [Keggle](https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews)

### Customer Segmentation
This research aims to gain insight into the sentiments of th e women customers using their review comments on clothing items. This section further discuss the research method, the sampling method and the data analysis procedure. Customer segmentation can be used by retailers to target individuals to improve their service, track customer sentiment over time, determine if a particular customer segment feel more strongly about your product, track how a change in product or service affects how customers feel.
  * #### Sentiment Analysis
	Afinn lexicon package was used to get the sentiment score of the women review texts in the database. AFINN is an English wordlist-based approach for sentiment analysis developed by Finn Årup Nielsen. Words scores range from minus five (negative) to plus five (positive). The current version of the lexicon is AFINN-en-165.txt and it contains over 3,300+ words with a polarity score associated with each word. Before applying AFINN score calculation Review texts were converted into lower case. Afinn scores for each review text were stored in the sent_score column. A positive score means positive sentiment and negative score means negative sentiment. To get the distribution on the positive side (>= 0) lowest negative score values were added into each score. The distribution plot drawn using the seaborn package showed skewed distribution for Age and sent_score variable. Hence, the Log values of the variables were calculated to get normal distribution.
  * #### K-Means Clustering
	K-Means clustering is a type of unsupervised machine learning that uses data that is not assigned to a specific category or group, called unlabeled data. The algorithm works assigns the data points values based on features that are inputted. K-Means clustering finds the most significant number of clusters and then determines the grouping of clusters based on the distance between the data points based on inputted attributes. As the K-mean clustering requires, normally distributed variables, log values were used to get the K value by the elbow method. From the graph, I selected the K value as 6. K-Mean from the sklearn package was applied to the data. The cluster graph was plotted using seaborn lmplot for age and sent_score. 

{% capture fig_img %}
![Foo]({{ '/assets/images/Clustering.png' | relative_url }})
{% endcapture %}

{{ fig_img | markdownify | remove: "
" | remove: "
" }} Segmenting customers based on their age and sentiment score

- *The ranters (unhappy customers, Cluster 0)* - In most businesses, this segment of customers will be handled by customer service team, but, don’t try to sell to them. Instead, we can ask them what we could change to make their experience better or ask them for their ideas to engage them.<br>
- *The ‘on the fence’ bunch (Cluster 1, 3 & 4)* - These are the trickiest group as it’s hard to get a true understanding into how they feel and whether or not the marketing efforts will be receptive or not. A good approach with this group could be to get ravers to engage with them.
- *The ravers (happy customers, Cluster 2, 5)* - We know they are happy, so let them tell the world. Give them some sort of incentive to promote your services on social media (small is fine and it will help drive repeat or additional purchases too). Their comment (positive word of mouth) next to an exclusive offer for their friends and family is ideal. This type of activity is often referred to as advocacy marketing.

### Recommendation
Any organization looking to do business on the internet is interested in what its customers have to say. We want to know if we can predict rating based on the content of the review using recommendation model. We also want to see if we can predict how likely a customer will recommend products to their friends. A recommender system, or a recommendation system, can be thought of as a subclass of information filtering system that seeks to predict the best “rating” or “preference” a user would give to an item which is typically obtained by optimizing for objectives like total clicks, total revenue, and overall sales. I used collaborative filtering with the inbuilt recommender algorithm in the surprise package and for the evaluation cross-validation was done with RMSE and MAE measurements. 

  * #### Scikit-Surprise
Surprise (Simple Python Recommendation System Engine) is a recommendation system library, which is one of the scikit series. Simple and easy to use, while supporting a variety of recommendation algorithms (basic algorithm, collaborative filtering, matrix decomposition, etc.). In Collaborative filtering, the model learns from the users past behaviour, user’s decision, and preference to predict items the user might have an interest in. Scikit-Surprise is an easy-to-use Python scikit for recommender systems.
For the analysis Age, Clothing ID, and Rating variables were chosen. Selected 25% of random records as a test set. Using the cross-validation method from surprise package evaluated RMSE and MAE scores on 5 folds for SVD, KNNBasic, KNNWithMeans, KNNWithZscore, BaselineOnly, and NormalPredictor algorithms. All algorithms showed similar RMSE and MAE values. I selected the BaselineOnly algorithm for building the model, because, a baseline prediction algorithm provides a set of predictions that you can evaluate as you would any predictions for your problems, such as classification accuracy or RMSE. 

|Algorithms	|Test_RMSE	|Test_MAE	|Fit_time	|Test_time |
|----------     |---------      |--------       |--------       |--------- |
|BaselineOnly	|1.098524	|0.883113	|0.025738	|0.023345  |
|KNNWithMeans	|1.121399	|0.891298	|0.153384	|0.908731  |
|KNNWithZScore	|1.124861	|0.892554	|0.146855	|0.947234  |
|KNNBasic	|1.127862	|0.886328	|0.147432	|0.955465  |
|SVD	        |1.132511	|0.903668	|0.974561	|0.021864  |
|NormalPredictor|1.427513	|1.083934	|0.029032	|0.027179  |

### [Github Repository](https://github.com/GARV3007/Data-Mining-codes/tree/master/Term%20Project){: .btn .btn--primary .btn--small}
