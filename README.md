# 🎬 Movies Recommender System

[![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-informational?logo=pandas)](https://pandas.pydata.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikit-learn)](https://scikit-learn.org/)
[![TMDB](https://img.shields.io/badge/Data-TMDB-red?logo=tmdb)](https://www.themoviedb.org/)

Welcome to the **Movies Recommender System**, a project designed to suggest movies to users using two powerful approaches:
- **🔍 Content-Based Filtering**
- **🔗 Hybrid Filtering (Content-Based + Collaborative Filtering)**

---

## 📁 Dataset

This project uses a dataset from Kaggle [Kaggle 💙](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset) 

| File Name           | Description |
|---------------------|-------------|
| `movies_metadata.csv` | 🗂 Metadata of ~45,000 movies, including release dates, budget, genres, etc. |
| `keywords.csv` | 🧩 Plot keywords (stringified JSON format) |
| `credits.csv` | 🎭 Cast and crew details (stringified JSON format) |
| `links_small.csv` | 🔗 IMDB and TMDB IDs for a 9,000 movie subset |
| `ratings_small.csv` | ⭐ 100,000 ratings from 700 users on 9,000 movies |

---

## 🛠️ Building Approach

### 🔹 Content-Based Filtering
We generate a **"soup"** feature by combining metadata like genres, director, keywords, and cast. This textual data is vectorized using **TF-IDF**, and we compute **cosine similarity** to recommend similar movies.

- 💡 Libraries: `TfidfVectorizer`, `CosineSimilarity`, `Pandas`, `Numpy`
- 🧠 No user data needed — purely based on movie features

### 🔸 Hybrid Filtering (Content + Collaborative)
To create a more **personalized experience**, we blend content-based methods with **collaborative filtering** using user ratings. This addresses the **cold-start problem** where new users or movies lack sufficient data.

- 📊 Ratings from `ratings_small.csv` form the user-movie interaction matrix
- 📚 Matrix Factorization / Neighborhood-based algorithms can be used
- 🤝 Users get recommendations based on both movie metadata *and* similar user preferences

---

## 🧰 Technologies Used

| Category | Tools/Libraries |
|---------|----------------|
| Language | Python |
| Data Processing | Pandas, NumPy |
| ML & Recommender Models | Scikit-learn, Surprise |
| NLP | Scikit-learn (TF-IDF) |
| Visualization | Matplotlib, Seaborn (optional) |

---

## 📌 Features

- ✅ Recommend similar movies using metadata
- ✅ Personalized hybrid recommendations using user preferences
- ✅ Handles cold-start problems better than standalone collaborative filtering
- ✅ Clean modular code ready for deployment

---

## 🚀 How to Run

```bash
# Clone the repo
git clone https://github.com/yourusername/movie-recommender.git
cd movie-recommender

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook Movie_Recommender_System.ipynb
```

# Acknowledgements
This dataset is an ensemble of data collected from TMDB and GroupLens.
The Movie Details, Credits and Keywords have been collected from the TMDB Open API. This product uses the TMDb API but is not endorsed or certified by TMDb. Their API also provides access to data on many additional movies, actors and actresses, crew members, and TV shows. You can try it for yourself here >> [TMBD API](https://developer.themoviedb.org/docs/getting-started)