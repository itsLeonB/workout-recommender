# Workout Recommender
The workout recommender system for FAIZ app. The system recommends three most similar workout for a selected workout. The recommendations are based on the workout description that is encoded to BERT embeddings.

## Dataset
The workouts that are used in this recommender system are obtained through the Gym Exercise Dataset available in [Kaggle](https://www.kaggle.com/datasets/niharika41298/gym-exercise-data). The dataset consists of workout names, workout descriptions, workout type, body part target, and difficulty level.

## Model
This system uses the BERT language model for [pre-processing](https://tfhub.dev/tensorflow/bert_en_uncased_preprocess/3) and [encoding](https://tfhub.dev/tensorflow/bert_en_uncased_L-12_H-768_A-12/4) the workout descriptions.

## Output Files
There are two different output files:

 1. `workout_dataset.csv`; this is the workout data that have been cleaned for use in the app's database and as the input for encoding.
 2. `encodings.pickle`; this is the encodings dataframe that is saved as a pickle file, used for calculating cosine similarity to give recommendations.

## Notebooks
Four notebooks are available:

 1. `workout_recommender.ipynb`; the main notebook for researching and experimenting on the recommender system.
 2. `dataset_preprocessing.ipynb`; dataset pre-preprocessing is done in this notebook.
 3. `encode_data.ipynb`; data encoding with BERT model is done in this notebook.
 4. `get_recom.ipynb`; retrieving recommendations by calculating the cosine similarities between datas is done in this notebook.

## Deployment
For deploying this recommender system,  we have built an API endpoint that loads the `encodings.pickle` file and retrieving workout ids. The API and its documentation can be accessed [here](https://github.com/itsLeonB/workout-recommender-api).