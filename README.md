# Music Recommender System

This project implements a music recommender system using K-Nearest Neighbors (KNN) to suggest similar songs based on audio features like danceability, energy, tempo, and loudness. The system uses a dataset of songs and provides song recommendations based on the input song.

## Requirements

To run the project, you need the following Python libraries:

- `pandas`
- `scikit-learn`

Install these libraries using `pip`:

```bash
pip install pandas scikit-learn

 
```
## How It Works

### 1. Load and Preprocess the Dataset

- The dataset is loaded using the `pandas` library.
- Relevant features such as **danceability**, **energy**, **tempo**, and **loudness** are selected for the recommendation system.
- These features are then normalized using **`StandardScaler`** from **`scikit-learn`** to standardize the values. This ensures that each feature contributes equally to the KNN algorithm, improving the model's accuracy.

### 2. Train the KNN Model

- The **K-Nearest Neighbors (KNN)** model is trained using the normalized features of the songs.
- The KNN algorithm calculates the distance between each song in the dataset and finds the nearest neighbors based on the selected features.
- The model uses the **Euclidean distance** to measure how similar the songs are to one another.

### 3. Make Recommendations

- When a song index is provided as input, the model identifies the **nearest neighbors** by calculating the Euclidean distance between the input song and other songs in the dataset.
- The model then returns a list of recommended songs that are similar to the input song, based on their feature values (e.g., danceability, energy, tempo, and loudness).
- The recommendations are displayed in terms of the **song title** and **artist**.

## Customization

### 1. Number of Recommendations

You can change the number of songs to be recommended by adjusting the `num_recommendations` parameter in the `recommend_songs()` function. For example, to get 10 recommendations instead of 5, simply update the function call:

```python
recommend_songs(song_index, num_recommendations=10)
```


### 2. Additional Features

To enhance the recommendations, you can include additional audio features in the dataset, such as **acousticness**, **valence**, **instrumentalness**, or any other relevant feature. Adding more features may improve the accuracy of the song recommendations, as the model will have more information to work with.

For example, if you add **acousticness** and **valence** to your dataset, the code would look like this:

```python
features = data[['danceability', 'energy', 'tempo', 'loudness', 'acousticness', 'valence']].values
```
### 3. Distance Metric

The KNN model uses **Euclidean distance** by default to find similar songs. However, you can experiment with other distance metrics like **Manhattan** or **Minkowski** by changing the `metric` parameter in the `NearestNeighbors` class. For example, to use **Manhattan distance**, modify the code as follows:

```python
knn = NearestNeighbors(n_neighbors=5, metric='manhattan')  # Using Manhattan distance

```
## Conclusion

This **Music Recommendation System** is based on the **K-Nearest Neighbors (KNN)** algorithm, allowing users to discover new songs that are similar to a given track. The system can be customized to fit your needs by adjusting the number of recommendations, experimenting with different distance metrics, or adding more features to improve the quality of recommendations.

## License

This project has **MIT License** .
