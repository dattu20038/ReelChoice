ReelChoice - Movie Recommendation System
========================================

Overview
--------

ReelChoice is a movie recommendation system built using Python and Streamlit. The system suggests movies based on the similarity of their attributes, such as genres, keywords, cast, crew, and overview. It utilizes pre-trained models and pickled data to generate recommendations dynamically.


======================================================================================================================================================================================================================================================================================================

Features
--------

*   Movie Recommendation: Based on the selected movie, the system recommends similar movies.
*   Interactive Interface: Users can select a movie from a list and get recommendations instantly.
*   Data Preprocessing: Uses movie data from a dataset containing movie details like genres, cast, and more.


================================================================================================================================================================================================================================================================================================================

Technologies Used
-----------------

*   Python: For backend processing and handling data.
*   Streamlit: For creating the web-based interactive interface.
*   Pandas: For data manipulation and cleaning.
*   Scikit-learn: For feature extraction and calculating similarity between movies.
*   Pickle: For saving and loading pre-processed data (movies dictionary and similarity matrix).


===============================================================================================================================================================================================================================================================================================================================================================

How to Use
----------

1.  Clone the repository:
    
    bash
    
    Copy code
    
    `git clone https://github.com/your-username/ReelChoice.git` 
    
2.  Navigate to the project directory:
    
    bash
    
    Copy code
    
    `cd ReelChoice` 
    
3.  Install the necessary dependencies:
    
    bash
    
    Copy code
    
    `pip install -r requirements.txt` 
    
4.  Run the Streamlit application:
    
    bash
    
    Copy code
    
    `streamlit run app.py` 
    
5.  Open the application in your browser to get movie recommendations.
    


================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================

Project Structure
-----------------

bash

Copy code

`ReelChoice/
├── app.py                # Streamlit app for the interface
├── movies_dict.pkl       # Pickled movies dictionary containing movie data
├── similarity.pkl        # Pickled similarity matrix for movie recommendations
├── tmdb_5000_movies.csv  # Movie data (CSV file)
├── tmdb_5000_credits.csv # Movie credits data (CSV file)
├── requirements.txt      # List of dependencies
└── README.md             # Project documentation` 






==============================================================================================================================================================================================================================================================================================================================================================================================================================================================================

Detailed Explanation
--------------------

### Data Preprocessing

The dataset consists of movie information such as genres, keywords, cast, and crew. The following preprocessing steps are performed:

1.  Merging Data: The `movies` dataframe is merged with `credits` based on the movie title to combine information from both files.
    
2.  Handling Missing Data: Any rows with missing data are dropped using the `dropna()` function.
    
3.  Data Conversion:
    
    *   The `genres`, `keywords`, and `cast` columns contain JSON strings. These strings are converted to Python lists using `ast.literal_eval()`, and we extract the relevant information (like genre names or cast members).
4.  Cleaning Data: Spaces are removed from strings in the `genres`, `keywords`, `cast`, `crew`, and `overview` columns.
    
5.  Feature Vectorization: The `CountVectorizer` from `sklearn` is used to convert text data (like genres and overview) into a numerical format suitable for similarity comparison.
    


======================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================================

### Movie Recommendation

The system uses the following steps to recommend movies:

1.  Similarity Matrix: A similarity matrix is pre-calculated based on features like genres, keywords, and cast. This matrix is loaded using Pickle.
    
2.  Recommendation Logic:
    
    *   When a user selects a movie, the system finds its index in the dataset and looks up its similarity scores.
    *   The system sorts the movies based on similarity scores and returns the top 5 most similar movies.


==================================================================================================================================================================================================================================================================================================================================================================================================================================================================================

### UI Elements

*   Select Movie: A dropdown allows the user to select a movie from the list.
*   Recommend Button: When clicked, it triggers the recommendation logic and displays the top 5 recommended movies.


=====================================================================================================================================================================================================

Future Improvements
-------------------

*   Enhance Recommendations: Use advanced algorithms like collaborative filtering or deep learning to improve recommendation accuracy.
*   Better UI: Add movie posters and more detailed information for each recommended movie.
*   Expand Data: Include additional data like ratings, reviews, and release year for more personalized recommendations.


=============================================================================================================================================================================================================================================================================================================================================================
