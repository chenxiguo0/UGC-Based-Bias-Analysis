---
editor: 
  markdown: 
    wrap: 72
---

# 2024-dsan-5000-project

## Project Overview

This project investigates whether online environments are more accommodating to liberal or conservative viewpoints by analyzing Reddit posts and comments. It predicts toxicity levels and evaluates the relative hostility directed toward opposing political perspectives.

The analysis combines unsupervised learning to cluster discussions into topics and supervised learning to classify texts' political leanings and assess toxicity levels. It aims to determine whether toxicity systematically differs by political orientation.

The goal is to explore potential biases in online political discussions and promote a more inclusive and respectful environment for all viewpoints.

## Data Collection and Processing

### Data Collection

-   Utilized PRAW (Python Reddit API Wrapper) to collect data from
    political subreddits
-   Gathered both "hot" and "controversial" posts along with their
    comments
-   Collected features include:
    -   Post title and content
    -   Comment text and hierarchy
    -   Upvote scores
    -   Creation timestamps
    -   Post flairs
-   For labeled training sets, this project used:
    -   training set for Decision Tree binary classification (liberal or
        conservative)

        [Liberal vs Conservative Title
        classification](https://www.kaggle.com/code/noname666666/liberal-vs-conservative-title-classification)

    -   training set for Random Forest regression (value between 0 and
        1)

        [Jigsaw Unintended Bias in Toxicity
        Classification](https://www.kaggle.com/c/jigsaw-unintended-bias-in-toxicity-classification/data)

### Data Cleaning

Text preprocessing pipeline: - Removed special characters, URLs, and
emoji - Converted text to lowercase - Filtered out non-English words -
Applied lemmatization using NLTK - Removed domain-specific stopwords -
Duplicate removal - NaN handling

## Analysis Methods

### Unsupervised Learning

#### Topic Modeling

-   Applied Non-negative Matrix Factorization (NMF) for topic discovery
-   Used TF-IDF vectorization
-   Performed dimensionality reduction using PCA and t-SNE
-   Identified 5 main political discussion topics:
    -   Abortion
    -   Gun Control
    -   Taxation
    -   Climate Change
    -   General Politics

#### Clustering

-   Implemented DBSCAN clustering
-   Compared clustering results with NMF topics
-   Visualized topic distributions across different subreddits

### Supervised Learning

#### Political Lean Classification

-   Implemented Decision Tree Classifier
-   Features:
    -   TF-IDF vectors (max_features=5000)
-   Hyperparameter optimization using GridSearchCV
-   Cross-validation for model evaluation

#### Toxicity Prediction

-   Random Forest Regressor for toxicity scoring
-   Features:
    -   TF-IDF vectors
-   Model evaluation metrics:
    -   MSE, RMSE, MAE
    -   R-squared
    -   Explained variance score

## Resources

### Project Website

Please access the project website at: [Project
Website](https://gcx1372.georgetown.domains/5000FinalProject/)

### Reddit API Usage

#### Documentation

Please view the Reddit API documentation at: [API
Documentation](https://www.reddit.com/dev/api/)

#### Registration

Please create a free Reddit application at: [API
Setup](https://www.reddit.com/prefs/apps)

### Data

Please access all the data used in this project at:
[Data](https://drive.google.com/drive/folders/1zFjMN6lln-fJmuv5N1Vgwww4QgnYrgg3?usp=drive_link)

### Code

Please access all the code run in this project at:
[Code](https://drive.google.com/drive/folders/1f4YfQcw_DcSVjU1bYt67iToqG7skpa4V?usp=drive_link)
