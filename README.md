# 🎬 Movie Recommendation System

A Content-Based Movie Recommendation System built using Python, Pandas, and Scikit-Learn. This project recommends similar movies based on genre information using TF-IDF Vectorization and Cosine Similarity.

## 📌 Project Overview

This recommendation system analyzes movie genres and suggests movies that are similar to a selected movie. The model uses Natural Language Processing (NLP) techniques to convert genre information into numerical vectors and then calculates similarity scores between movies.

For example, if a user searches for:

> Toy Story (1995)

The system returns the top 5 movies with genres most similar to Toy Story.

---

## 🚀 Features

- Content-Based Recommendation System
- Genre-based movie similarity
- TF-IDF Vectorization
- Cosine Similarity Calculation
- Fast movie recommendations
- Simple and easy-to-understand implementation

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-Learn
- TF-IDF Vectorizer
- Cosine Similarity

---

## 📂 Dataset

This project uses the MovieLens Dataset containing:

### movies.csv
- movieId
- title
- genres

### ratings.csv
- userId
- movieId
- rating
- timestamp

Dataset Source:
MovieLens Dataset

---

## ⚙️ Working Process

### 1. Data Loading

Load movie and rating datasets.

```python
movies = pd.read_csv("movies.csv")
ratings = pd.read_csv("ratings.csv")
```

### 2. Data Preprocessing

Replace genre separators (`|`) with spaces.

```python
movies['genres'] = movies['genres'].str.replace('|', ' ')
```

### 3. TF-IDF Vectorization

Convert textual genre information into numerical vectors.

```python
tfidf = TfidfVectorizer(stop_words='english')
tfidf_matrix = tfidf.fit_transform(movies['genres'])
```

### 4. Similarity Calculation

Compute cosine similarity between all movies.

```python
cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
```

### 5. Recommendation Generation

Recommend top 5 most similar movies.

```python
recommend_movies("Toy Story (1995)")
```

---

## 📊 Recommendation Logic

The system:

1. Finds the selected movie.
2. Retrieves its genre vector.
3. Calculates similarity with all other movies.
4. Sorts movies by similarity score.
5. Returns the top 5 recommendations.

---

## 💻 Example Usage

```python
recommend_movies("Toy Story (1995)")
```

### Sample Output

```text
Toy Story 2 (1999)
A Bug's Life (1998)
Monsters, Inc. (2001)
Finding Nemo (2003)
Shrek (2001)
```

(Note: Actual recommendations may vary depending on dataset version.)

---

## 📈 Future Improvements

- Collaborative Filtering
- Hybrid Recommendation System
- User-Based Recommendations
- Deep Learning-Based Recommendations
- Streamlit Web Application
- Movie Poster Integration
- Recommendation API using Flask

---

## 📁 Project Structure

```text
Movie-Recommendation-System/
│
├── movie.ipynb
├── movies.csv
├── ratings.csv
├── README.md
└── requirements.txt
```

---

## 🔧 Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/movie-recommendation-system.git
```

Move to project directory:

```bash
cd movie-recommendation-system
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook
```

---

## 📋 Requirements

```text
pandas
numpy
scikit-learn
jupyter
```

---

## 🎯 Key Learning Outcomes

- Content-Based Recommendation Systems
- Natural Language Processing Basics
- TF-IDF Vectorization
- Cosine Similarity
- Feature Engineering for Text Data
- Building Recommendation Engines

---

## 👨‍💻 Author

Dhruv

Aspiring Machine Learning Engineer | Data Science Enthusiast

---

⭐ If you found this project useful, consider giving it a star on GitHub.
