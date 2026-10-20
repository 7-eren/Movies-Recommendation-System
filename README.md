# 🎬 Movie Recommendation System

A content-based movie recommendation web app built with **Python**, **Pandas**, **Streamlit**, and **scikit-learn**. It uses Natural Language Processing (NLP), TF-IDF vectorization, and cosine similarity to recommend movies with similar textual characteristics.

## Features

- Recommend movies based on genres, keywords, overview, cast, and director.
- TF-IDF converts movie text into numerical vectors.
- Cosine similarity ranks movies by textual similarity.
- Interactive Streamlit interface.
- Upload your own CSV dataset.
- Includes a small sample dataset so you can run the project immediately.

## Project structure

```text
movie-recommendation-system/
├── app.py
├── recommender.py
├── requirements.txt
├── README.md
├── .gitignore
└── data/
    └── sample_movies.csv
```

## Requirements

- Python 3.10 or newer
- Internet access for installing Python dependencies
- Visual Studio Code or another Python editor (optional)

## Run locally

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR-USERNAME/movie-recommendation-system.git
   cd movie-recommendation-system
   ```

2. **Create and activate a virtual environment**

   Windows:
   ```bash
   python -m venv .venv
   .venv\Scripts\activate
   ```

   macOS/Linux:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch the app**
   ```bash
   streamlit run app.py
   ```

Streamlit will print a local URL, usually `http://localhost:8501`, which you can open in your browser.

## Dataset format

Your CSV must include a `title` column and at least one supported text feature. The app uses any of these columns when present:

- `genres`
- `keywords`
- `overview`
- `cast`
- `director`

A simple dataset may instead use `description`, `plot`, or `summary`. Missing feature values are handled as empty strings. Column names should match the names above.

The included `data/sample_movies.csv` is a small demonstration dataset, not a complete commercial movie catalogue. For richer recommendations, use a larger dataset that you have permission to use and redistribute.

## How it works

1. Load the movie dataset.
2. Clean missing text values.
3. Combine available movie features into one text field.
4. Apply `TfidfVectorizer` to represent the text numerically.
5. Calculate cosine similarity between movie vectors.
6. Rank similar movies and return the requested number, excluding the selected movie.

## Limitations

- Recommendations reflect textual similarity, not guaranteed personal taste.
- Output quality depends on the dataset's accuracy and detail.
- This version does not learn from user ratings or watch history.
- The sample dataset is intentionally small and only demonstrates the workflow.

## Future improvements

- Movie posters and external movie metadata.
- User profiles, ratings, and watch history.
- Hybrid recommendations combining content and collaborative filtering.
- Semantic embeddings and recommendation evaluation.
- Deployment to a public hosting platform.

## References

- [Python documentation](https://docs.python.org/3/)
- [Pandas documentation](https://pandas.pydata.org/docs/)
- [scikit-learn TF-IDF Vectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)
- [scikit-learn cosine similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html)
- [Streamlit documentation](https://docs.streamlit.io/)

## License

Choose a license before accepting outside contributions or redistributing the project. If you want others to reuse the code, the MIT License is a common permissive option.
