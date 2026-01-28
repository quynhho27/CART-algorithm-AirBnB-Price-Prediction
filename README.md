## PROJECT OVERVIEW

This project applies CART (Classification and Regression Trees) to analyze and predict Airbnb housing prices using a real-world Airbnb dataset. The study is designed as a comprehensive end-to-end machine learning pipeline, covering EDA, preprocessing, feature engineering, model tuning, and model comparison.

The project is formulated into two related tasks:

- Regression: Predicting the continuous housing price
- Classification: Predicting whether a listing belongs to a high-price or low-price segment

## EDA

EDA is conducted to establish a clear understanding of the dataset and guide modeling decisions:

- Distribution analysis
- Detection of skewness and extreme outliers
- Missing value analysis

## REGRESSION MODELING

***1. Preprocessing***
- Outlier handling using Winsorization
- Feature engineering: Creation of Cartesian coordinate features from latitude and longitude
- Skewness correction: Box-Cox transformation, Yeo-Johnson transformation

***2. Univarite Tree***
- Trained regression trees using individual features
- Hyperparameter tuning performed with:
  + RandomizedSearchCV
  + GridSearchCV
- Models evaluated using regression performance metrics: MAE/MSE/R-squared
- Best R-squared: 65%

***3. Multivariate Tree***
- Three weighting strategies:

  + Target Correlation Weighting: Features weighted based on correlation strength with the target variable
  + Feature Importance Weighting: Weights derived from feature importance scores
  + OLS-based Weighting: Linear regression coefficients used as feature weights

- Each weighting strategy is used to:
  + Construct composite features
  + Train multivariate CART models
  + Compare performance against univariate CART

- Best R-squared:
  + Target Correlation Weighting: 64.5%
  + Feature Importance Weighting: 64.6%
  + OLS-based Weighting: 64.6%

## CLASSIFICATION MODELING

***1. Preprocessing***
- Feature engineering: Creation of Cartesian coordinate features from latitude and longitude
- Skewness correction: Box-Cox transformation, Yeo-Johnson transformation

***2. Univarite Tree***
- GridSearchCV used to identify optimal hyperparameters
- Tree pruning applied to control overfitting
- Models evaluated using classification performance metrics: accuracy, precsion, recall, F1-score
- Best Accuracy: 81%

***3. Multivariate Tree***
- Three weighting strategies:

  + Target Correlation Weighting: Features weighted based on correlation strength with the target variable
  + Feature Importance Weighting: Weights derived from feature importance scores
  + OLS-based Weighting: Linear regression coefficients used as feature weights

- Each weighting strategy is used to:
  + Construct composite features
  + Train multivariate CART models
  + Compare performance against univariate CART

- Best Accuracy
  + Target Correlation Weighting: 88%
  + Feature Importance Weighting: 89.4%
  + OLS-based Weighting: 91.7%

 ## MODEL COMPARISON

 A comprehensive comparison is conducted across CART, ID3 and C4.5

- Regression: CART performs best among all tree-based models
- Classification: ID3 outperforms CART and C4.5

## TOOLS
- Python (Pandas, Scikit-learn, Matplotlib, Seaborn)
- Jupyter Notebook
