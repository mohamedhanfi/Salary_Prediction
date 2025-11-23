# 💰 Salary Prediction Model
# 🎯 Project Overview
This repository contains a comprehensive Machine Learning solution for predicting employee salaries. The project is structured as a Regression task, leveraging various employment and demographic features to estimate the salary_in_usd. The core goals include:

Establishing a robust preprocessing pipeline to handle categorical and high-cardinality features.

Developing a highly accurate non-linear regression model.

Providing reproducible code for salary forecasting and market analysis.

# 💾 Dataset Details
The model is trained on the Dataset salary 2024.csv file, which captures employee compensation data across multiple years and countries.

Key Features:
Target Variable: salary_in_usd (the final output)

Time: work_year

Hierarchical Features: experience_level (e.g., Entry, Senior)

Nominal Features: employment_type (e.g., Full Time, Contract)

High-Cardinality Features: job_title, company_location

# 🛠 Preprocessing and Feature Engineering
The quality of the input data is critical for high accuracy. The following transformations were applied to the raw data:

Categorical Feature Handling:
Mapping: Initial code mappings (e.g., EN to Entry-level) were applied for readability.

Ordinal Encoding: Applied to the experience_level feature, as it has a clear, ordered ranking which aids model learning.

One-Hot Encoding (OHE): Used for nominal features like employment_type.

Strategies for High Cardinality:
Job Title: To prevent overfitting, low-frequency job titles (appearing fewer than [TODO: Insert your chosen threshold, e.g., 10] times) were grouped into an 'Other' category before applying OHE.

Company Location: Target Encoding was used, replacing each location with the average salary_in_usd associated with that location. This dramatically reduces the feature count while preserving the valuable information about location-based salary premiums.

Numerical Preparation:
Scaling: After the train/test split, all numerical features were scaled using StandardScaler to normalize their distribution, ensuring equal contribution to the model's loss function.

# 🧠 Model Selection and Training
Algorithm Choice:
The problem was approached using Gradient Boosting techniques, which are highly effective for structured data regression problems due to their ability to capture complex, non-linear feature interactions.

Model: [TODO: Insert your final chosen model, e.g., XGBoost Regressor or LightGBM]

Hyperparameter Optimization:
Strategy: The model was tuned using [TODO: Insert Tuning Method, e.g., Grid Search or Randomized Search] combined with K-Fold Cross-Validation (K=5) on the training set.

Objective: The tuning process prioritized minimizing the Root Mean Squared Error (RMSE) to achieve the lowest overall prediction error.

Evaluation:
The final model was validated on a separate, unseen test set, using RMSE and Mean Absolute Error (MAE) to assess performance.
