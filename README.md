# Can Taylor Swift songs be sorted into albums based on their audio features?

# Introduction
The goal of this project is to determine whether Spotify audio features can be used to classify which album a Taylor Swift song belongs to. Each album represents a distinct musical era, and this project investigates whether those differences are reflected in measurable audio characteristics.

Choosing this as my project topic was important to me because I have liked Taylor Swift for many years and her impact on the music industry has been monumental. This project helps explain how musical features varying across albums show how my favorite artist’s sound evolves over time.

My research question: Can Spotify audio features be used to classify the album of a Taylor Swift song?

My hypothesis: Although there might be some separability in the data, due to each album having songs that range from slow to upbeat, it will be difficult to clearly classify songs into specific albums soley based on audio features.

## The Dataset

This dataset was sourced from [GitHub](https://github.com/wjakethompson/taylor) and the data in the repository was sourced from Spotify API. The original dataset contains all of Taylor Swift's songs and information about them such as release date, what album each song is from, what artists wrote it, and whether or not it is explicit or not. It also contains features about the songs, such as their tempo and acousticness. The dataset contains tracks spanning her entire career up to THE TORTURED POETS DEPARTMENT, including The Taylor Swift Holiday Collection, and does not include her most recent album, The Life of a Showgirl.

For my project, I am keeping the columns that have the album name of songs, audio features of the song, and dropping rows with missing values

# Data Cleaning and Preparation

Features/Units:
- Tempo: The speed of a track measured in Beats per Minute (BPM).
- Loudness: Overall loudness of a track measured in Decibels (dB).
- Duration: Length of the song measured in Milliseconds (ms).
- Energy, Danceability, Acousticness, Valence, Speechiness: Continuous values from 0.0 to 1.0 representing the intensity or presence of the respective attribute.

# Methodology

To investigate the research question, the project follows the standard data science workflow:

- Exploratory Data Analysis (EDA): Visualizing feature distributions across albums using Seaborn boxplots and correlation heatmaps.
- Dimensionality Reduction: Using Principal Component Analysis (PCA) to visualize song clusters in 2D space.
- Classification Models: (1) Multinomial Logistic Regression:Serving as a linear baseline for multi-album classification. (2) PCA + Logistic Regression Pipeline: Testing if reducing feature noise improves accuracy.

# Results

- Accuracy: The model achieved an accuracy of about 20% across 16 albums. While numerically low, this is better than random guessing (around 6%).
- Separability: Visual clustering via PCA showed that distinct genres are measier for the model to isolate than similar eras.
- Limitations: Audio features alone lack the lyrical context that define Taylor's albums.

# Conclusion

This project explored whether Spotify audio features can be used to sort Taylor Swift songs into her albums. While album classification is challenging due to stylistic overlap, both models demonstrated that audio features contain meaningful information about musical eras.

Regularized dimensionality reduction using PCA slightly improved model stability, suggesting that feature correlation plays a role in classification performance. Future work could include incorporating lyrical features or comparing Taylor Swift’s albums to those of other artists.
