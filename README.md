ReelChoice - Movie Recommendation System
========================================

Overview
--------

ReelChoice is a movie recommendation system built using Streamlit, pandas, and machine learning techniques. The system provides movie suggestions based on the user’s selected movie by calculating similarity with other movies. It utilizes data from the TMDB dataset, processes it, and recommends movies based on their features like genres, keywords, cast, and crew.

Features
--------

*   **Movie Search**: Users can search for movies from a list of popular movies.
*   **Movie Recommendations**: Based on the movie selected, the system will recommend 5 similar movies using a similarity matrix.
*   **Data Processing**: The system processes movie metadata such as genres, keywords, cast, and crew.
*   **Streamlit Interface**: The user interface is built using Streamlit to provide a simple and interactive web application for movie recommendations.

Files
-----

*   **movies\_dict.pkl**: A serialized file that contains the movie data.
*   **similarity.pkl**: A serialized file containing the similarity matrix of movies.
*   **tmdb\_5000\_movies.csv**: Contains movie information such as movie\_id, title, and overview.
*   **tmdb\_5000\_credits.csv**: Contains information on movie credits such as cast and crew.

Setup
-----

### Prerequisites

Before running the system, ensure you have the following dependencies installed:

*   pandas
*   numpy
*   streamlit
*   scikit-learn
*   ast
*   pickle

You can install the required dependencies using the following command:

bash

Copy code

`pip install pandas numpy streamlit scikit-learn ast` 

### Running the App

1.  Clone the repository to your local machine:

bash

Copy code

`git clone https://github.com/your-username/ReelChoice.git
cd ReelChoice` 

2.  Place the required data files (such as `movies_dict.pkl`, `similarity.pkl`, `tmdb_5000_movies.csv`, and `tmdb_5000_credits.csv`) in the project directory.
    
3.  Run the app using Streamlit:
    

bash

Copy code

`streamlit run app.py` 

This will start the application and open it in your default web browser.

Code Explanation
----------------

### Data Processing

1.  **Merging Data**: We merge movie metadata and credit information into a single dataset.
2.  **Handling Missing Data**: Any missing values are dropped to ensure clean data for processing.
3.  **Feature Extraction**: The movie data is processed to extract relevant features such as genres, keywords, cast, and crew. These features are then converted to a suitable format for text-based similarity calculation.
4.  **Text Preprocessing**: The text fields such as genres, keywords, and overview are cleaned and formatted to remove extra spaces and simplify the text.

### Recommendation Logic

The recommendation function is based on calculating the similarity between movies using a cosine similarity matrix. The function:

*   Finds the index of the selected movie.
*   Computes the distances of the selected movie from all other movies.
*   Sorts the movies based on similarity and returns the top 5 similar movies.

### User Interface

The Streamlit interface allows users to:

*   Select a movie from the dropdown list.
*   Get movie recommendations by clicking the "Recommend" button.

### Example Usage

When you run the app, you will see a dropdown list of movie titles. After selecting a movie, you can click on the "Recommend" button to see a list of movies that are similar to the one you selected.
