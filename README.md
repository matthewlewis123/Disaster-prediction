# Disaster Prediction

This project aims to predict disaster-related tweets using machine learning techniques as a part of the "Natural Language Processing with Disaster Tweets" Kaggle competition. The notebook `DISASTER_PREDICTION.ipynb` contains the entire workflow, from data preprocessing to model training and evaluation.

## Table of Contents

- Installation
- Usage
- Data
- Model
- Evaluation
- Results
- License

## Installation

To run the notebook, you need to install the required libraries. You can install them using the following command:

```bash
pip install numpy pandas tqdm matplotlib sentence-transformers scikit-learn tensorflow
```

## Usage

1. **Load the Training Data**: The training data is loaded from `train.csv` and is provided by Kaggle.
2. **Data Preprocessing**: Text embeddings are generated using the `SentenceTransformer` package and several models from obtained with the help of the MTEB leaderboard.
3. **Database Storage**: The embeddings are stored in an SQLite database for easy retrieval.
4. **Model Training**: A neural network is trained on the text embeddings to predict disaster-related tweets.
5. **Evaluation**: The model is evaluated on a validation and test set.
6. **Prediction**: The model is used to predict disaster-related tweets on a new dataset (`test.csv`) provided by Kaggle.

## Data

The dataset consists of tweets labeled as disaster-related (1) or not (0). The columns in the dataset are:

- `id`: Unique identifier for each tweet.
- `keyword`: A keyword from the tweet.
- `location`: The location where the tweet was sent from.
- `text`: The text of the tweet.
- `target`: The label indicating whether the tweet is disaster-related (1) or not (0).

## Model

The model is a neural network built using TensorFlow and Keras. It consists of several dense layers with LeakyReLU activations, batch normalization, and dropout for regularization. The optimizer used is Adagrad with a learning rate scheduler to reduce the learning rate on plateau.

## Evaluation

The model is evaluated using binary accuracy and binary cross-entropy loss. The training and validation losses and accuracies are plotted to visualize the model's performance over epochs.

## Results

The predictions are saved in a CSV file named `predictions_submissions.csv`. The number of predictions for each class (0 and 1) is also printed. The best results are store in `predictions_submissions_kaggle.csv`


## License

This project is licensed under the MIT License. See the LICENSE file for details.
