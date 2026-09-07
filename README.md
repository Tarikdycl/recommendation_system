# Recommendation System From Scratch

A hands-on recommendation systems project built from scratch in Python.

This project starts with simple collaborative filtering and gradually progresses toward matrix factorization, gradient-based training, regularization, bias terms, model evaluation, hyperparameter tuning, and finally a real-world MovieLens implementation.

## What I Built

### 1. User-Based Collaborative Filtering

- User-item rating matrix
- Common rating extraction
- Cosine similarity
- Mean-centered similarity
- Similar-user ranking
- Weighted recommendation scoring
- Top-K recommendations

### 2. Matrix Factorization

The recommender represents users and movies using learned latent feature vectors.

The rating matrix is approximated as:

R ≈ U @ V.T

Where:

- R = observed user-item ratings
- U = user latent feature matrix
- V = movie latent feature matrix
- U @ V.T = predicted rating matrix

Each predicted rating is based on the dot product between a user vector and a movie vector.

### 3. Training From Scratch

The latent user and movie vectors are trained using Stochastic Gradient Descent.

Implemented concepts include:

- Prediction error
- Mean Squared Error
- Stochastic Gradient Descent
- Train/test rating split
- RMSE evaluation
- L2 regularization

### 4. Bias-Aware Matrix Factorization

The prediction model was extended to include global, user, and movie biases:

r_hat = global_mean + user_bias + movie_bias + user_vector · movie_vector

This allows the model to capture:

- overall rating tendencies
- users who generally rate higher or lower
- movies that generally receive higher or lower ratings
- personalized user-movie interactions

On the synthetic dataset, adding bias terms improved test RMSE from approximately 1.31 to approximately 0.95.

### 5. Hyperparameter Experiments

The model was tested using different:

- latent feature dimensions
- regularization strengths

Best result on the synthetic dataset:

- Latent features: 2
- Regularization: 0.02
- Test RMSE: approximately 0.803

The experiments also demonstrated that increasing model complexity does not always improve generalization.

### 6. MovieLens Real-World Evaluation

The model was then applied to the MovieLens dataset.

Dataset preparation included:

- loading ratings and movie metadata
- checking missing values
- inspecting rating distributions
- mapping original user and movie IDs to matrix indices
- creating train and test splits
- training directly from observed rating rows

MovieLens dataset used:

- 100,836 ratings
- 610 users
- 9,724 rated movies

Final model performance:

- Train RMSE: approximately 0.776
- Test RMSE: approximately 0.881

The final model generates Top-K recommendations for unseen movies using learned user and movie representations.

Example recommendations for a MovieLens user included:

- Casablanca (1942)
- The Shawshank Redemption (1994)
- Dr. Strangelove (1964)
- The Great Escape (1963)
- Rear Window (1954)
- The Godfather: Part II (1974)

## Project Structure

recommendation_system/
│
├── notebooks/
│   ├── 01_similarity_basics.ipynb
│   ├── 02_matrix_factorization.ipynb
│   └── 03_movielens_recommender.ipynb
│
├── data/
├── src/
├── README.md
├── requirements.txt
└── .gitignore

## Concepts Practiced

### Python

- Functions
- Dictionaries
- Lists
- Tuples
- Loops
- Sorting
- Lambda functions
- NumPy arrays
- Pandas DataFrames
- Boolean masks
- Matrix operations
- DataFrame mapping
- Iterating over rating observations

### Linear Algebra

- Vectors
- Dot product
- Vector magnitude
- Cosine similarity
- Matrix multiplication
- Matrix transpose
- User-item matrices
- Latent factor matrices

### Machine Learning

- Collaborative filtering
- Matrix factorization
- Latent representations
- Gradient descent
- Stochastic Gradient Descent
- Loss functions
- Train/test evaluation
- RMSE
- Overfitting
- L2 regularization
- Global, user, and movie biases
- Hyperparameter tuning
- Top-K recommendation ranking

## Goal

The goal of this project was not only to use recommendation-system libraries, but to understand and implement the underlying mathematics and algorithms from scratch before applying them to a real-world dataset.

The project progressed from hand-built similarity calculations to a bias-aware matrix factorization model trained and evaluated on MovieLens.