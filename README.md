# youtube-engagement-prediction

## Problem Statement
As Youtube continues to grow in popularity, content creation on the platform has become mainstream and can be a viable source of income for the creators that operate on it. One issue that these channels may run into is trying to determine what subjects to create content on and then how to structure the video and structure description in a manner that optimizes engagement for the channel.

## Project Overview
By connecting to the Youtube API and generating a sample dataset of videos and channels, the team mined and analyzed features to create a model that will predict a video’s weighted engagement score (Likes + 2*Comments).


## Data Exploration
I used "engagement" as the target variable. The first try: Engagement = 2 * comment + likes (I weight comments higher).

## Feature Mining
I use categorical variables and numeric variables who have significant predicting power, and drop other variables who have little association with the target.
For some numeric variables, I changed them into categorical or dummy variables.

For text data (video description, video title, etc), I extracted keywords from them using NLP, especially nltk package. Then I use Word2Vec and TSNE, and transfer text into vectors. I made a visualization of the key words clusters in low dimension. And I use those clusters as new features for prediction.

## Model Performance
While Random Forest had the highest accuracy, the current apparent over fitting leads the team to select Linear Regression the purpose of this exercise.
As additional channels/videos were added, RMSE, prediction, and over-fitting improved.
Additional models that were tested were Gradiant Boosting and Bagging Classifier.
Models were ran on  3 different sets of features while optimizing.
We believes that the low Test RMSE associated with test data was related to the sample size and characteristics of this dataset.

The updated model is optimized when using Decision Tree, but still suffers from some level of overfitting and would benefit from a larger sample of channels and videos.
