# 🎌 Anime Recommendation System

[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-green.svg)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3+-red.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📖 Overview

An end-to-end **Anime Recommendation System** built using collaborative filtering and content-based filtering techniques. This project analyzes user ratings and anime genres to provide personalized anime recommendations using machine learning algorithms.

## 🎯 Features

### 🤝 Collaborative Filtering
- User-based collaborative filtering using K-Nearest Neighbors (KNN)
- Cosine similarity metric for finding similar anime
- Sparse matrix optimization for efficient computation
- Filters users with at least 200 ratings for quality recommendations

### 📚 Content-Based Filtering
- TF-IDF vectorization on anime genres with n-gram range (1-3)
- Sigmoid kernel similarity computation
- Genre-based anime recommendations

### 📊 Data Visualization
- Top 10 anime by user ratings (bar plot)
- Top 10 anime by community size/members (bar plot)
- Rating distributions comparison (website ratings vs user ratings)
- Interactive pie chart for anime type distribution (TV, Movie, OVA, ONA, Special, Music)
- Genre word cloud visualization

### 🔧 Data Preprocessing
- Handling missing values (-1 ratings converted to NaN)
- Removing duplicate entries
- Filtering low-activity users
- Text cleaning for anime titles (HTML entities removal)

## 📊 Dataset

- **Source**: [Anime Recommendations Database](https://www.kaggle.com/datasets/CooperUnion/anime-recommendations-database) from Kaggle
- **Files**:
  - `anime.csv`: 12,294 anime entries with metadata (genre, type, episodes, rating, members)
  - `rating.csv`: 7,813,737 user ratings from 73,516 users

### Dataset Schema

**anime.csv**
| Column | Description |
|--------|-------------|
| anime_id | Unique identifier for each anime |
| name | Anime title |
| genre | Comma-separated genres |
| type | Medium (TV, Movie, OVA, ONA, Special, Music) |
| episodes | Number of episodes |
| rating | Average website rating |
| members | Number of community members |

**rating.csv**
| Column | Description |
|--------|-------------|
| user_id | Unique user identifier |
| anime_id | References anime.csv |
| rating | User rating (1-10, -1 = unwatched) |

## 🛠️ Technologies Used

### Core Libraries
- **Python 3.9+** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations

### Machine Learning
- **Scikit-learn** - KNN model, TF-IDF vectorization, sigmoid kernel
- **SciPy** - Sparse matrix operations

### Visualization
- **Matplotlib** - Basic plotting
- **Seaborn** - Statistical visualizations
- **Plotly** - Interactive pie charts
- **WordCloud** - Genre frequency visualization

### Development
- **Jupyter Notebook** - Interactive development environment

## 📈 Key Insights from Analysis

1. **Rating Distribution**
   - Most ratings are concentrated between 6-10
   - Mode of distribution around 7.5-8.0
   - Both distributions (website and user) are left-skewed

2. **Anime Distribution by Type**
   - TV: 67.9% of all anime
   - Movies: 13.4%
   - OVA: 9.97%
   - ONA: 1.2%

3. **Popular Anime Metrics**
   - Top-rated anime based on user rating counts
   - Largest community sizes by member count

## 🚀 How It Works

### 1. Collaborative Filtering (User-Based)

```python
# Creates user-item rating matrix
anime_pivot = anime_feature.pivot_table(
    index='anime_title', 
    columns='user_id', 
    values='user_rating'
).fillna(0)

# Applies KNN with cosine similarity
model_knn = NearestNeighbors(metric='cosine', algorithm='brute')
model_knn.fit(csr_matrix(anime_pivot.values))

# Finds similar anime
distances, indices = model_knn.kneighbors(query_vector, n_neighbors=6)# 🎌 Anime Recommendation System

[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.0+-green.svg)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-1.3+-red.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 📖 Overview

An end-to-end **Anime Recommendation System** built using collaborative filtering and content-based filtering techniques. This project analyzes user ratings and anime genres to provide personalized anime recommendations using machine learning algorithms.

## 🎯 Features

### 🤝 Collaborative Filtering
- User-based collaborative filtering using K-Nearest Neighbors (KNN)
- Cosine similarity metric for finding similar anime
- Sparse matrix optimization for efficient computation
- Filters users with at least 200 ratings for quality recommendations

### 📚 Content-Based Filtering
- TF-IDF vectorization on anime genres with n-gram range (1-3)
- Sigmoid kernel similarity computation
- Genre-based anime recommendations

### 📊 Data Visualization
- Top 10 anime by user ratings (bar plot)
- Top 10 anime by community size/members (bar plot)
- Rating distributions comparison (website ratings vs user ratings)
- Interactive pie chart for anime type distribution (TV, Movie, OVA, ONA, Special, Music)
- Genre word cloud visualization

### 🔧 Data Preprocessing
- Handling missing values (-1 ratings converted to NaN)
- Removing duplicate entries
- Filtering low-activity users
- Text cleaning for anime titles (HTML entities removal)

## 📊 Dataset

- **Source**: [Anime Recommendations Database](https://www.kaggle.com/datasets/CooperUnion/anime-recommendations-database) from Kaggle
- **Files**:
  - `anime.csv`: 12,294 anime entries with metadata (genre, type, episodes, rating, members)
  - `rating.csv`: 7,813,737 user ratings from 73,516 users

### Dataset Schema

**anime.csv**
| Column | Description |
|--------|-------------|
| anime_id | Unique identifier for each anime |
| name | Anime title |
| genre | Comma-separated genres |
| type | Medium (TV, Movie, OVA, ONA, Special, Music) |
| episodes | Number of episodes |
| rating | Average website rating |
| members | Number of community members |

**rating.csv**
| Column | Description |
|--------|-------------|
| user_id | Unique user identifier |
| anime_id | References anime.csv |
| rating | User rating (1-10, -1 = unwatched) |

## 🛠️ Technologies Used

### Core Libraries
- **Python 3.9+** - Programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations

### Machine Learning
- **Scikit-learn** - KNN model, TF-IDF vectorization, sigmoid kernel
- **SciPy** - Sparse matrix operations

### Visualization
- **Matplotlib** - Basic plotting
- **Seaborn** - Statistical visualizations
- **Plotly** - Interactive pie charts
- **WordCloud** - Genre frequency visualization

### Development
- **Jupyter Notebook** - Interactive development environment

## 📈 Key Insights from Analysis

1. **Rating Distribution**
   - Most ratings are concentrated between 6-10
   - Mode of distribution around 7.5-8.0
   - Both distributions (website and user) are left-skewed

2. **Anime Distribution by Type**
   - TV: 67.9% of all anime
   - Movies: 13.4%
   - OVA: 9.97%
   - ONA: 1.2%

3. **Popular Anime Metrics**
   - Top-rated anime based on user rating counts
   - Largest community sizes by member count

## 🚀 How It Works

### 1. Collaborative Filtering (User-Based)

```python
# Creates user-item rating matrix
anime_pivot = anime_feature.pivot_table(
    index='anime_title', 
    columns='user_id', 
    values='user_rating'
).fillna(0)

# Applies KNN with cosine similarity
model_knn = NearestNeighbors(metric='cosine', algorithm='brute')
model_knn.fit(csr_matrix(anime_pivot.values))

# Finds similar anime
distances, indices = model_knn.kneighbors(query_vector, n_neighbors=6)
# TF-IDF vectorization on genres
tfv = TfidfVectorizer(
    min_df=3, 
    analyzer='word',
    ngram_range=(1, 3),
    stop_words='english'
)
tfv_matrix = tfv.fit_transform(genres_str)

# Sigmoid kernel similarity
sig = sigmoid_kernel(tfv_matrix, tfv_matrix)

# Returns top 10 similar anime by genre
anime-recommendation-system/
│
├── Anime_Recommendation_System.ipynb   # Main Jupyter notebook
├── anime.csv                          # Anime metadata (not included in repo)
├── rating.csv                         # User ratings (not included in repo)
├── requirements.txt                   # Python dependencies
├── README.md                          # Project documentation
├── LICENSE                            # MIT License
└── .gitignore                         # Git ignore file
