\# Recommendation System From Scratch



A hands-on recommendation systems project built from scratch in Python.



This project starts with simple collaborative filtering and gradually progresses toward matrix factorization, gradient-based training, regularization, bias terms, model evaluation, and hyperparameter tuning.



\## What I Built



\### 1. User-Based Collaborative Filtering



\- User-item rating matrix

\- Common rating extraction

\- Cosine similarity

\- Mean-centered similarity

\- Similar-user ranking

\- Weighted recommendation scoring

\- Top-K recommendations



\### 2. Matrix Factorization



The recommender represents users and movies using learned latent feature vectors.



The rating matrix is approximated as:



R ≈ U @ V.T



Where:



\- R = observed user-item ratings

\- U = user latent feature matrix

\- V = movie latent feature matrix

\- U @ V.T = predicted rating matrix



Each predicted rating is initially based on the dot product between a user vector and a movie vector.



\### 3. Training From Scratch



The latent user and movie vectors are trained using Stochastic Gradient Descent.



Implemented concepts include:



\- Prediction error

\- Mean Squared Error

\- Stochastic Gradient Descent

\- Train/test rating split

\- RMSE evaluation

\- L2 regularization



\### 4. Bias-Aware Matrix Factorization



The prediction model was extended to include global, user, and movie biases:



r\_hat = global\_mean + user\_bias + movie\_bias + user\_vector · movie\_vector



This allows the model to distinguish between:



\- overall rating tendencies

\- users who generally rate higher or lower

\- movies that generally receive higher or lower ratings

\- personalized user-movie interactions



Adding bias terms improved test performance significantly on the current synthetic dataset.



\### 5. Hyperparameter Experiments



The model was tested using different:



\- latent feature dimensions

\- regularization strengths



Best result on the current synthetic dataset:



\- Latent features: 2

\- Regularization: 0.02

\- Test RMSE: approximately 0.803



The experiments also demonstrated that increasing model complexity does not always improve generalization.



\## Project Structure



recommendation\_system/

│

├── notebooks/

│   ├── 01\_similarity\_basics.ipynb

│   ├── 02\_matrix\_factorization.ipynb

│   └── 03\_movielens\_recommender.ipynb

│

├── src/

├── README.md

├── requirements.txt

└── .gitignore



\## Concepts Practiced



\### Python



\- Functions

\- Dictionaries

\- Lists

\- Tuples

\- Loops

\- Sorting

\- Lambda functions

\- NumPy arrays

\- Boolean masks

\- Matrix operations



\### Linear Algebra



\- Vectors

\- Dot product

\- Vector magnitude

\- Cosine similarity

\- Matrix multiplication

\- Matrix transpose

\- User-item matrices

\- Latent factor matrices



\### Machine Learning



\- Collaborative filtering

\- Matrix factorization

\- Latent representations

\- Gradient descent

\- Stochastic Gradient Descent

\- Loss functions

\- Train/test evaluation

\- RMSE

\- Overfitting

\- L2 regularization

\- User and item biases

\- Hyperparameter tuning



\## Current Status



The recommendation algorithms have currently been implemented and tested from scratch using a small synthetic dataset.



The next stage of the project is to apply the same ideas to the MovieLens dataset.



Planned next steps:



\- Load and explore MovieLens ratings

\- Build a real user-item dataset

\- Create training and test splits

\- Train the bias-aware matrix factorization model

\- Evaluate performance using RMSE

\- Generate Top-K movie recommendations

\- Refactor reusable model logic into the `src/` directory



\## Goal



The goal of this project is not only to use recommendation-system libraries, but to understand and implement the underlying mathematics and algorithms from scratch before applying them to a real-world dataset.

