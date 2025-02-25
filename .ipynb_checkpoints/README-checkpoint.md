# Movie Recommendation System

This project implements a simple **content-based recommendation system** for movies. Given a short text description of a user's preferences, the system processes the input and returns the top 5 most similar movies based on enriched textual features from the dataset.

---

## Overview

The recommendation system leverages TF-IDF vectorization and cosine similarity to compare a user's query against a combined text summary of each movie. The enriched summary is created by merging multiple columns (such as genres, keywords, cast, and overview) into a single text field to provide richer context.

---

## Dataset

- **Movies Data:**  
  - `tmdb_500_movies.csv`: Contains details for 500 movies.
- **Credits Data:**  
  - `tmdb_500_credits.csv`: Contains information on cast and crew for 500 movies.
- **Source:**  
  - Both files are created by taking the first 500 rows from the larger datasets `tmdb_5000_movies.csv` and `tmdb_5000_credits.csv`, respectively, which can be downloaded from [Kaggle: TMDB Movie Metadata](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata?select=tmdb_5000_movies.csv).
- **Preprocessing:**  
  - The datasets are merged on movie IDs.
  - Columns that store lists of dictionaries (e.g., genres, keywords, cast) are converted to a comma-separated string format.
  - Missing values are filled, and text is lowercased for consistency.

*The datasets are stored in the `data/` folder.ed in the `data/` folder.*

---

## Approach

1. **Data Enrichment:**  
   - Relevant columns (genres, keywords, overview, title, tagline, cast) are combined into a single text summary for each movie.
   - The text is preprocessed using tokenization, lemmatization, and stopword removal (using NLTK) to enhance its quality.

2. **Vectorization:**  
   - The enriched summaries are transformed into TF-IDF vectors using scikit-learn's `TfidfVectorizer`, which converts the text into a numerical representation.

3. **Similarity Computation:**  
   - The user's query is similarly vectorized.
   - Cosine similarity is computed between the user's query vector and each movie's TF-IDF vector.

4. **Recommendation:**  
   - Movies are ranked based on similarity scores.
   - The top 5 movies with the highest scores are returned as recommendations.
  
---

## Salary Expectation

I'm looking for an intern salary in the range of $20 to $30, but I'm open to negotiation.