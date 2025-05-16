# TMDB Movie Data Analysis: Uncovering Genre Trends and Release Patterns 🎬

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg) ![Libraries](https://img.shields.io/badge/libraries-pandas%2C%20numpy%2C%20matplotlib%2C%20seaborn-orange.svg) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## 🌟 Overview

This project dives into the TMDB movie dataset, a rich collection of information on over 10,000 movies. The primary goal is to perform an Exploratory Data Analysis (EDA) to identify patterns and trends related to movie genres and release years. By cleaning, transforming, and visualizing the data, we aim to answer specific questions about the film industry's landscape.

## 🎯 Key Questions Addressed

This analysis seeks to answer the following:

1.  Which genres had the largest release of movies (or which are the most popular genres based on the number of releases)?
2.  Which year saw the highest number of movie releases?

## 💾 Dataset

The dataset used is `tmdb_movies.csv`, containing various attributes for movies, including:
*   `id`: Unique identifier for each movie.
*   `genres`: A pipe-separated string of genres associated with the movie.
*   `original_title`: The original title of the movie.
*   `cast`: Main actors.
*   `director`: Director(s) of the movie.
*   `release_year`: The year the movie was released.
*   `budget_adj`, `revenue_adj`: Budget and revenue adjusted for inflation.
*   And several other features.

*Source: This dataset is a modified version often found on platforms like Kaggle, originally derived from The Movie Database (TMDB) API.*

## 🛠️ Methodology

The analysis follows a structured approach:

1.  **Data Loading & Initial Inspection:**
    *   Loaded the dataset using Pandas.
    *   Initial review of data types, missing values, and basic statistics.

2.  **Data Cleaning & Preprocessing:**
    *   **Column Removal:** Dropped irrelevant columns (e.g., `imdb_id`, `homepage`, `tagline`, `keywords`, `production_companies`, `budget`, `cast`) to streamline the dataset for the defined objectives.
    *   **Duplicate Removal:** Identified and removed duplicate entries to ensure data integrity.
    *   **Missing Value Imputation:**
        *   Replaced zero values in `runtime`, `budget_adj`, and `revenue_adj` with their respective column means. This was done to preserve data points for analysis, assuming zero indicates missing or erroneous data rather than an actual value of zero.
        *   Filled missing values in derived genre columns (`genres_2`, `genres_3`) with placeholder strings ("No 2nd genre", "No 3rd genre") to handle movies with fewer than three listed genres.
    *   **Data Type Conversion:** Converted `release_date` to datetime objects and `release_year` to integer type for easier manipulation and analysis.

3.  **Feature Engineering:**
    *   **Genre Splitting:** The `genres` column (pipe-separated strings) was split into multiple individual genre columns (`genres_1`, `genres_2`, `genres_3`) to enable granular analysis of each listed genre. Columns beyond the third genre were dropped due to high sparsity.

4.  **Exploratory Data Analysis & Visualization:**
    *   **Genre Popularity:**
        *   Aggregated counts of each unique genre across all genre columns.
        *   Visualized genre frequencies using bar charts and line plots (Matplotlib & Seaborn) to identify the most common genres.
    *   **Release Year Trends:**
        *   Grouped movie data by `release_year` and counted the number of releases per year.
        *   Visualized this trend to pinpoint the year with the highest movie output.

## 📊 Key Findings

*   **Most Popular Genre(s):** The analysis revealed that **Drama** was the most frequently occurring genre, appearing in >50% of the movies. Other prominent genres included **Comedy** and **Thriller**.
*   **Peak Release Year:** The year with the highest number of movie releases was **2014**, with more than **600** movies released.

## ⚙️ Technologies Used

*   **Python 3.x**
*   **Pandas:** For data manipulation and analysis.
*   **NumPy:** For numerical operations.
*   **Matplotlib:** For creating static, interactive, and animated visualizations.
*   **Seaborn:** For enhanced statistical data visualization.
*   **Jupyter Notebook:** As the development environment.

## 🚀 How to Run This Project

1.  **Prerequisites:**
    *   Python 3.8 or higher
    *   Git
    *   pip (Python package installer)

2.  **Clone the Repository:**
    ```bash
    git clone https://github.com/OptimusAI01/Movies-Data-Analysis.git
    cd Investigating the Movies
    ```

3.  **Install Dependencies:**
    It's recommended to use a virtual environment.
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

4.  **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook Investigating_the_movies.ipynb
    ```
    *(Rename your `.ipynb` file to something descriptive like `TMDB_Movie_Analysis.ipynb` if it's not already)*

5.  Run the cells in the notebook to see the analysis.

## 💡 Potential Future Improvements

*   Investigate cast and director impact on movie popularity or revenue.
*   Apply sentiment analysis to movie overviews or description using another dataset.

## 📄 License

This project is licensed under the MIT License. Have fun!

---

_This README was crafted with care by OptimusAI01._
