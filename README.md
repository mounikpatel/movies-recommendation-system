# Movies Recommendation System [![ForTheBadge built-with-love](http://ForTheBadge.com/images/badges/built-with-love.svg)](https://GitHub.com/Naereen/)

Recommend movies based on inputs provided by user, such as :

1. Number of movies for recommendations
2. From_year
3. To_year
4. Genre (for content-based)/Movie title with release year (for collaborative filtering)

## Background

[![Typing SVG](https://readme-typing-svg.herokuapp.com?font=bebas+neue&color=E51904&vCenter=true&lines=Inspired+by+NETFLIX)](https://git.io/typing-svg)

## Introduction

With the rapid explosion of video streaming platforms on the Internet, the catalog of movies is rising exponentially, leaving viewers overwhelmed with a huge database of movies to choose from. Movie Recommendation Systems come into play, which consider users' preferences and recommend movies to them. This saves users a lot of time and effort that would otherwise be wasted while searching for a movie manually. This motivated me to start research on the topic ‘Movies Recommendation’.

## Data Source

Two different datasets from [MovieLens](https://grouplens.org/datasets/movielens/) that were collected by the GroupLens Research team for research work in the field of recommender systems were used. They are as follows:

1. [MovieLens 25M Dataset](https://grouplens.org/datasets/movielens/25m/): Approximately 63 thousand movies and 25 million user-ratings
2. [MovieLens Latest Small Dataset](https://grouplens.org/datasets/movielens/latest/): Approximately 10 thousand movies and 100 thousand user-ratings

## Code Notebooks

[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com)
[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Naereen/badges)

### 1. [Top-N Popular Movies Recommender System](https://github.com/mounikpatel/movies-recommendation-system/blob/main/Top_N_Popular_Movies_Recommender_System.ipynb)

Recommends Top-N Popular Movies to the user when the user inputs the number of movies for recommendations, from_year, to_year and genre. The Movies Recommender System will take year_range and genre into account and filter the movie list. This movie list will be again filtered by only selecting movies which have a rating higher than the average rating and the number of users who rated the movie higher than the average count. Finally, the selected movie list will be sorted by the number of users who rated the movie in descending order and only top-N movies will be provided as recommendations.

### 2. [Top-N Rated Movies Recommender System](https://github.com/mounikpatel/movies-recommendation-system/blob/main/Top_N_Rated_Movies_Recommender_System.ipynb)

Recommends Top-N Rated Movies to the user when the user inputs the number of movies for recommendations, from_year, to_year and genre. The Movies Recommender System will take year_range and genre into account and filter the movie list. This movie list will be again filtered by only selecting movies which have a rating higher than the average rating and the number of users who rated the movie higher than the average count. Finally, the selected movie list will be sorted by average rating of the movie in descending order and only top-N movies will be provided as recommendations.

### 3. [Top-N Similar Movies Recommender System (by Cosine Similarity)](https://github.com/mounikpatel/movies-recommendation-system/blob/main/Top_N_Similar_(User_Rated)_Movies_Recommender_System_(by_Cosine_Similarity).ipynb)

Recommends Top-N Similar Movies (by Cosine Similarity) to the user when the user inputs the number of movies for recommendations, from_year, to_year and movie title with release year. The Movies Recommender System will take year_range into account and filter the movie list. A user-ratings matrix will be created for each user to rate different movies. User-ratings of input movie titles will be selected and similarity will be calculated with user-ratings of other movies using cosine similarity. These will result in a list of movies which have similar user-ratings as that of the input movie. Further, this list of movies will be sorted by cosine similarity score in descending order and only the top 0.01% of users-rated movies will be selected. Finally, top-N movies will be provided as recommendations.

### 4. [Top-N Similar Movies Recommender System (by Pearson Correlation)](https://github.com/mounikpatel/movies-recommendation-system/blob/main/Top_N_Similar_(User_Rated)_Movies_Recommender_System_(by_Pearson_Correlation).ipynb)

Recommends Top-N Similar Movies (by Pearson Correlation) to the user when the user inputs the number of movies for recommendations, from_year, to_year and movie title with release year. The Movies Recommender System will take year_range into account and filter the movie list. A user-ratings matrix will be created for each user to rate different movies. User-ratings of input movie titles will be selected and similarity will be calculated with user-ratings of other movies using pearson correlation. These will result in a list of movies which have similar user-ratings as that of the input movie. Further, this list of movies will be sorted by Pearson correlation score in descending order and only the top 0.01% of users-rated movies will be selected. Finally, top-N movies will be provided as recommendations.

## Libraries Used

1. [NumPy](https://numpy.org/): NumPy is the most significant Python package for scientific computing. It is a Python library that includes a multidimensional array object, several derivative objects (such as masked arrays and matrices), and a collection of functions for performing rapid array operations.
2. [Pandas](https://pandas.pydata.org/): Pandas is an open source data analysis and manipulation tool built on top of the Python programming language that is quick, powerful, versatile, and user-friendly. It is a Python library provides high-performance, user-friendly data structures and data analysis tools.
3. [Scikit-learn](https://scikit-learn.org/stable/): Scikit-learn is an open-source machine learning library that can do both supervised and unsupervised learning. It also includes tools for model fitting, data preprocessing, model selection and evaluation, and a variety of other functions.

## Deployment

1. Download the zipped code file from repository main page or you can click here: [DOWNLOAD CODE](https://github.com/mounikpatel/movies-recommendation-system/archive/refs/heads/main.zip)
2. Unzip the .ipynp notebook of movie recommender system which you want to deploy.
3. Open [Google Colab] -> Go to 'File' tab -> Select 'Upload notebook'. 
   - *Note: You must have Google account signed-in before using Colab.*
4. Once the .ipynb notebook is uploaded -> Go to 'Runtime' tab -> Select 'Run all'.
5. You can try to give your own inputs in last cell 'Function Call' to get movie recommendations.

## Demo

1. Example screenshot of recommendations result provided by Top-N Popular Movies Recommender System

<img src="https://user-images.githubusercontent.com/36979317/129491261-6df1d117-ab61-43ff-97d9-fdac43c2807e.JPG" width="500"/>

2. Example screenshot of recommendations result provided by Top-N Rated Movies Recommender System

<img src="https://user-images.githubusercontent.com/36979317/129491286-e646afad-79d0-4c64-8282-1b2b133e75fd.JPG" width="500"/>

3. Example screenshot of recommendations result provided by Top-N Similar Movies Recommender System (by Cosine Similarity)

<img src="https://user-images.githubusercontent.com/36979317/129491309-d8b0a7dd-4e38-42fa-a96a-61e7a5e6f01f.JPG" width="500"/>

4. Example screenshot of recommendations result provided by Top-N Similar Movies Recommender System (by Pearson Correlation)

<img src="https://user-images.githubusercontent.com/36979317/129491338-2cda9f0c-0f23-43c1-8939-dc512d65e410.JPG" width="500"/>

## Author

[Mounik Patel](https://github.com/mounikpatel)

## Acknowledgment

Thanks to [Dr. T](https://github.com/trevortomesh)
