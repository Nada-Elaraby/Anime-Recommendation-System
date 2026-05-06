# 🎌 Anime Recommendation System

[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📖 Overview

An end-to-end **Anime Recommendation System** built using collaborative filtering and content-based filtering techniques. This project analyzes user ratings and anime genres to provide personalized anime recommendations.

## 🎯 Features

- **Collaborative Filtering** using K-Nearest Neighbors (KNN) with cosine similarity
- **Content-Based Filtering** using TF-IDF vectorization on anime genres
- **Interactive visualizations** including:
  - Top 10 anime by ratings and community size
  - Rating distributions (website vs user ratings)
  - Genre word cloud
  - Anime type distribution (TV, Movie, OVA, etc.)
- **Data preprocessing** handling missing values (-1 ratings converted to NaN)
- **Sparse matrix optimization** for efficient computation

## 📊 Dataset

- **Source**: [Anime Recommendations Database](https://www.kaggle.com/datasets/CooperUnion/anime-recommendations-database) from Kaggle
- **Files**:
  - `anime.csv`: 12,294 anime entries with metadata (genre, type, episodes, rating, members)
  - `rating.csv`: 7,813,737 user ratings

## 🛠️ Technologies Used

- **Python 3.9+**
- **Pandas & NumPy** - Data manipulation
- **Scikit-learn** - KNN model, TF-IDF vectorization
- **Matplotlib & Seaborn** - Data visualization
- **Plotly** - Interactive pie charts
- **WordCloud** - Genre visualization
- **SciPy** - Sparse matrix operations

## 📈 Key Insights

- Most anime ratings are distributed between 6-10
- ~67.9% of anime are aired on TV, followed by movies (13.4%)
- Approximately 10% of anime are streamed as OVA
- Users with at least 200 ratings were retained for collaborative filtering

## 🚀 How It Works

### Collaborative Filtering (User-Based)
1. Creates a user-item rating matrix (anime × users)
2. Applies KNN with cosine similarity to find similar anime
3. Filters users with ≥ 200 ratings for quality

### Content-Based Filtering (Genre-Based)
1. Extracts genres from anime data
2. Applies TF-IDF vectorization with n-gram range (1-3)
3. Computes sigmoid kernel similarity matrix
4. Returns top 10 similar anime based on genre similarity

## 📂 Project Structure
