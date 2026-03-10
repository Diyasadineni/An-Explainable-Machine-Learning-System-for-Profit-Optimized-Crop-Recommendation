This project presents a profit-oriented crop recommendation system that analyzes agricultural production data and market price trends to identify the most profitable crops for different regions. The system combines machine learning models with economic indicators and explainable AI techniques to support data-driven agricultural decision making.

Unlike traditional crop recommendation systems that focus mainly on soil or climatic suitability, this framework prioritizes economic profitability by integrating crop yield data with mandi (market) price analytics.

Project Objectives

Predict crop profitability using agricultural production and market price data

Identify the most profitable crops for different states and districts

Apply machine learning models for profit prediction

Use explainable AI techniques to interpret model decisions

Provide data-driven insights for farmers and agricultural planners

Datasets

The project uses two publicly available datasets sourced from Kaggle:

Crop Yield Dataset
Contains agricultural production statistics including:

State

District

Crop

Area cultivated

Production

Yield

Crop year

Season

Mandi Price Dataset
Contains agricultural market price information including:

State

District

Commodity (Crop)

Modal price

Price date

These datasets were combined to build a profit modeling dataset by merging crop production information with market price data.

Technologies Used

Python

Pandas

NumPy

Scikit-Learn

Matplotlib

Seaborn

SHAP (Explainable AI)

ALE (Accumulated Local Effects)

Machine Learning Models

The project implements multiple models to predict crop profitability:

Linear Regression (Baseline Model)

Random Forest Regressor

Hyperparameter tuned Random Forest

Model performance is evaluated using:

R² Score

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

Explainable AI

To improve model transparency and interpretability, the project integrates:

SHAP (SHapley Additive Explanations)
Used to analyze feature importance and understand how different variables influence profitability predictions.

ALE (Accumulated Local Effects)
Used to analyze how individual features affect model predictions while accounting for feature interactions.

Key Features

Integration of crop yield and mandi price data

Profit-based crop recommendation framework

Machine learning based profitability prediction

Explainable AI using SHAP and ALE

State and district level crop ranking

Advanced feature engineering and economic indicators

Data visualization and correlation analysis

Output

The system provides:

Profit prediction for crops

Ranking of crops by profitability for a region

Feature importance explanations

Visualization of relationships between agricultural and economic factors
