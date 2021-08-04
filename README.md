# Capstone-Project: Sentiment Analysis on Food reviews

## Problem Statement
Many e-commerce prompt users to leave a review after purchasing an item from their website to understand a customer's experience. Reviews can affect another customers' decision on whether to purchase or not. Customers would judge the quality of an item based on previous customers' feedback. As part of the data scientist team in Consultancy of food product, we aim to classify the sentiment of reviews and to see if there are any potential roadblocks to customers' satisfaction.

## Background
Amazon.com Inc. is an American multinational technology company. It started out as an online bookseller and expanded its offerings to include music, clothings and a vast assortment of merchandise. It grown into an e-commerce behemoth. Currently, it is one of the prime site that shoppers would browse to buy anything from food to electronics.

With an increase in online shopping, giving reviews and ratings are how customers give feedback for businesses to understand the needs and wants of users. Using the wide range of food products that Amazon sell, we will conduct an analysis on its fine food dataset to categorize the sentiments of reviews.

Dataset: https://www.kaggle.com/snap/amazon-fine-food-reviews

## Executive Summary
We started by cleaning the dataset, keeping the reviews of the latest year that the dataset has and to overcome the unbalanced dataset, we did abit of undersampling from the majority class.

We pre-processed our text by removing html tags, stopwords, non-letters, convert to lowercase and stem them, followed by splitting the dataset into train and test set.

We did some exploratory data analysis on train dataset and here are our findings:

The average length of reviews were longer for negative sentiment.
Customers found extreme ends of the review (Rating 1 and 5) to be the most helpful
Food reviews were made up of text of people comparing it against a benchmark to express their likes/dislikes.
Next, we fit the dataset into logisitic regression, naive bayes, support vector classifier and long short term memory recurrent neural network to classify the reviews' sentiment.

Our machine learning and deep learning models outperformed VADER when determining a review sentiment, with deep learning being the winner.

Some topics in reviews that customers were dissatisfied about were Instant coffee and tea, bottled drinks, ingredient quality, pricey products, sugary snacks and pet food. Manufacturers could focus on improving their products, focuses on qualities that customers are concerned about and offering discounts to low quality products.

## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|Id|int|reviews|asin, e.g. amazon.com/dp/(id)| 
|UserId|object|reviews|id of user| 
|ProfileName|object|reviews|name of user| 
|HelpfulnessNumerator|object|reviews|number of users who found review helpful| 
|HelpfulnessDenominator|int|reviews|total number of users who indicated if they found the review helpful or not| 
|Score|int|reviews|rating of product| 
|Time|int|reviews|time of review (Unix)| 
|Summary|object|reviews|review summary| 
|Text|object|reviews|review text|

## Recommendations and conclusions
The model that performed the best was Bidirectional LSTM, consisting of 3 layer neural network - Bidirectional LSTM with 50 nodes, followed by a dense layer with 10 nodes and then an output layer with 1 node. With an accuracy of 0.89 and recall of 0.83 on validation set, the model serves as a good start for group the reviews into positive or negative sentiment and understand customers' preferences. Furthermore, on unseen data, with an even more unbalanced dataset, the model did well on the minority class, with a recall score of 0.79

Misclassification occurs when there are a mix of polarity in a review, at one point indicating it was good and another point indicating it as bad or in a particular review, customers may be talking about different things, with some good and some bad.

Topics that customers were dissatisfied about - Instant coffee and tea, bottled drinks, ingredient quality, pricey products, sugary snacks and pet food. Manufacturers could focus on improving their products, focuses on qualities that customers are concerned about and offering discounts to low quality products.

Further enhancement to this project can be made, we can do further in-depth analysis in topic modeling and further tune the neural network.


Note: Due to the limited space on github, datasets files could not be uploaded and hence is stored in this link instead:
https://drive.google.com/drive/folders/1cbmyzor3_Sq91RAC6qdAC4K5BeHTsXG7?usp=sharing
