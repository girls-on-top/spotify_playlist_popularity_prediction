# What makes a playlist popular?

Music plays an important role in the real life, and recommending suitable and popular playlists to users becomes a struggle for some music apps. Some previous articles had already come up with several models but the results were all not satisfying, so how to evaluate the popularity of a playlist remains unsolved. We aim to find out what makes a playlist popular and predicts the next hit focusing on data collected by Spotify.

## Introduction
Recommending playlists for people is important to both apps and their users. On the one hand, providing songs that users prefer will win the favor of them, and also makes life much easier for someone struggling in choosing or cannot find any favorite. On the other hand, bad recommendation makes people feel frustrated or irritable.

Therefore, finding out the features a popular playlist may have becomes the centerpiece of this article. The aim of this paper is to work with the public data set on AIcrowd develop a predictive model for the popularity for a Spotify playlist. To make the problem easier, the popularity of a playlist is defined by the number of followers.

## Original data
We use original data set provided by [AIcrowd](https://www.aicrowd.com/challenges/spotify-million-playlist-dataset-challenge)

## Data Acquiring and Cleaning

Considering the data from the data set is limited, we also retrieve other data that might be useful through [Spotify API](https://developer.spotify.com/documentation/web-api/).

## Feature Engineering

Based on intuition and domain knowledge, we do some feature engineering to transform some raw data into probably more informative forms.

Features are created in terms of the following questions:
- How many tracks in a playlist belong to the same artist?
- How many tracks in a playlist come from the same album? 
- What are top 50 genres words that have the highest frequencies?
- etc.

## Modeling and Evaluation

Four models we chose are:

- Multiple Linear Regression
- Random Forest
- XGBoost
- LightGBM

Models are built through grid search and fine tuning. Evaluation results are clearly shown and compared through analysis.

## Conclusion
We would like to explore what makes a Spotify playlist popular and predict on the number of followers for the playlists. We make use of data sets from AICrowd and also retrieve possibly useful data through Spotify API. Considering the imbalance of the data, with most of the playlists having very few number of followers and only a few playlists having many followers, we performed downsampling. We also do some feature engineering based on intuitive and domain knowledge to create new variables to be used to fit the models.

The variable have_description has the highest feature importance, meaning that whether or not the playlist has a description is important for whether or not the playlist is popular. The following important features are duration_s, the total time of the tracks in the playlist, and num_edits, the number of times the playlist has been edited. The feature track$\_$artist$\_$homo also shows up as a important feature in most of the models.
