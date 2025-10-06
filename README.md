Movie Recommender System (Content-Based) This project implements a Content-Based Movie Recommender System built using Python, Pandas, and Scikit-learn. It analyzes the characteristics of a movie (genres, cast, director, keywords, and plot summary) to suggest other movies with similar content.

A key feature of this system is the integration of fuzzy search, which allows users to get recommendations even if they only type a partial or slightly misspelled movie title.

✨ Features Content-Based Filtering: Recommendations are based on the tags of the movies, which include genres, keywords, top 3 cast members, and the director.

Vectorization: Uses CountVectorizer to transform the movie tags into a numerical vector space.

Similarity Metric: Utilizes Cosine Similarity to measure the distance (similarity) between movie vectors.

User-Friendly Search: The recommend() function handles non-exact matches by suggesting up to 5 close titles and prompting the user for selection.

⚙️ Methodology Overview The recommendation process follows these main steps:

Data Acquisition: Merging the tmdb_5000_movies.csv and tmdb_5000_credits.csv files.

Preprocessing & Tag Creation: Extracting nested data (like genres and cast) and consolidating key features into a single tags string for each movie. Spaces are removed from names (e.g., "Science Fiction" → "ScienceFiction") to treat them as single entities.

Stemming: Applying the Porter Stemmer (from nltk) to normalize words (e.g., 'actors', 'acting' → 'act').

Vectorization: Converting the stemmed tags into a numerical matrix using CountVectorizer (limiting to the top 5000 most frequent words).

Similarity Matrix: Calculating the cosine_similarity between every movie's vector to create a matrix where the value at (i,j) represents the similarity between Movie i and Movie j.

Recommendation: When a movie is input, the function retrieves its row from the similarity matrix and sorts the results to find the top 5 most similar movies.

🛠️ Installation and Setup Prerequisites Python 3.x

The following libraries:

pandas

numpy

scikit-learn

nltk

difflib (Standard library, usually included Screenshot 2025-10-06 194105 Screenshot 2025-10-06 194014
