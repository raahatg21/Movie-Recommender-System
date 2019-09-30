# Movie Recommender System

A recommender system gives recommendations to the user based on his/her ratings to recently watched titles, ratings of other users who watched the same title, general trends, etc. There are many kinds of recommender system, two are implemented in this project.

- Simple Recommender System
- Content Based Recommender System

# Simple Recommender System

Simple recommenders offer generalised recommendations to every user, based on movie popularity and/or genre. The basic idea behind this system is that movies that are more popular and critically acclaimed will have a higher probability of being liked by the average audience.  The output will be same for all users and all products.

## Dataset used

IMDB Dataset (https://drive.google.com/drive/u/0/folders/1KZ6EMemuKRnA5UmaFdbCTJ-W7d_GlAjI)
It is derived from MovieLens 20M Dataset.

## Workflow

- Load the data of all movies on IMDB
- Select a threshold as minimum number of votes, and reject all movies below that votes
- Select a metric for ranking and sort the list based on that metric
- Output top 15 movies of the sorted list

## How to run
Run the ipynb fie `simple_recommender.ipynb`. 

## Requirements

- Python 3
- Numpy
- Pandas

# Content Based Recommender System

Content-based recommenders suggest similar items based on a particular item. This system uses item metadata, such as genre, director, description, actors, etc. for movies, to make these recommendations. The general idea behind these recommender systems is that if a person liked a particular item, he or she will also like an item that is similar to it.

## Dataset used

IMDB Dataset (https://drive.google.com/drive/u/0/folders/1KZ6EMemuKRnA5UmaFdbCTJ-W7d_GlAjI)
It is derived from MovieLens 20M Dataset.

## Workflow

1) Plot/Description Based Recommender
  - Select the 'overview' of each movie
  - Convert it into TF-IDF vectors and construct TF-IDF matrix
  - Calculate the similarity score using cosine similarity
  - User inputs a movie title
    - We find similarity scores of all movies w.r.t. that title
    - Sort them
    - Select the 10 most similar movies to input movie

2) Credits, Genres and Keywords based Recommender
  - Get the credits and keywords for each movie from separate csv files and merge them into the current dataframe
  - Convert them from 'stringified' lists to a from that is more suitable to us
  - Clean the data, convert them into lower case, and remove spaces
  - Join these features to create a 'metadata soup'
  - Convert this soup into vectorised format using Count Vectorizer
  - Calculate cosine similarity from the Count matrix
  - Use the existing `get_recommendations()` function to get movie recommendations using this cosine similarity

## How to run
Run the ipynb fie `content_recommender.ipynb`. 

## Requirements

- Python 3
- Numpy
- Pandas
- Scikit Learn





