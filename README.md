ReelChoice
==========

ReelChoice is a web-based movie recommendation system that suggests movies based on the similarity of their attributes, such as genres, keywords, cast, crew, and overview. Built using Python and Streamlit, it provides dynamic recommendations through pre-trained models and pickled data.

Features
--------

*   **Movie Recommendation**: Select a movie to get top 5 similar movie recommendations based on movie attributes.
*   **Interactive Interface**: A simple dropdown allows users to select movies and get instant recommendations.
*   **Data Preprocessing**: Prepares movie data by handling missing data and converting JSON-like data into useful features.

Technologies Used
-----------------

*   Python
*   Streamlit
*   Pandas
*   Scikit-learn
*   Pickle

How to Use
----------

### Clone the repository

bash

Copy code

`git clone https://github.com/your-username/ReelChoice.git` 

### Navigate to the project directory

bash

Copy code

`cd ReelChoice` 

### Install dependencies

Copy code

`pip install -r requirements.txt` 

### Run the Streamlit application

arduino

Copy code

`streamlit run app.py` 

Open the application in your browser to get movie recommendations.

Project Structure
-----------------

bash

Copy code

`ReelChoice/
├── app.py             # Streamlit app for the interface
├── movies_dict.pkl    # Pickled movies dictionary containing movie data
├── similarity.pkl     # Pickled similarity matrix for movie recommendations
├── tmdb_5000_movies.csv # Movie data (CSV file)
├── tmdb_5000_credits.csv # Movie credits data (CSV file)
├── requirements.txt   # List of dependencies
└── README.md          # Project documentation` 

Detailed Explanation
--------------------

### Data Preprocessing

The dataset is preprocessed to prepare the movie data for recommendation:

1.  **Merging Data**: The `movies` dataframe is merged with `credits` to combine details from both files.
2.  **Handling Missing Data**: Missing values are removed using `dropna()`.
3.  **Data Conversion**:
    *   The `genres`, `keywords`, and `cast` columns are converted from JSON strings to Python lists.
    *   Relevant attributes (like genre names or cast members) are extracted from the lists.
4.  **Cleaning Data**: Spaces are removed from string values in `genres`, `keywords`, `cast`, `crew`, and `overview` columns.
5.  **Feature Vectorization**: The `CountVectorizer` from `sklearn` is used to convert text data (like genres and overview) into numerical features for similarity calculations.

### Movie Recommendation

1.  **Similarity Matrix**: A pre-calculated similarity matrix is loaded from the `similarity.pkl` file. This matrix contains similarity scores for all movies based on their features.
2.  **Recommendation Logic**:
    *   When a user selects a movie, the system identifies its index and fetches its similarity scores.
    *   The system sorts movies by similarity and returns the top 5 most similar movies.

### UI Elements

*   **Select Movie**: Dropdown menu for users to choose a movie.
*   **Recommend Button**: When clicked, it triggers the recommendation process and displays top 5 movie suggestions.

Future Improvements
-------------------

*   **Enhanced Recommendations**: Implement collaborative filtering or deep learning models for better recommendation accuracy.
*   **Better UI**: Add movie posters and more detailed information about the recommended movies.
*   **Expanded Data**: Include additional features like ratings, reviews, or release year for more personalized recommendations.

4o mini
