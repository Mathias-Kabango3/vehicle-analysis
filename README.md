# CO₂ Emissions Prediction

This project uses machine learning techniques to predict vehicle CO₂ emissions based on various engine and fuel efficiency features. It provides a reproducible pipeline from data exploration and preprocessing to model training and evaluation.

## Project Description

Given a dataset of vehicles with features such as engine size, fuel type, consumption metrics, and environmental scores, this project builds a regression(RandomForest regressor) model to predict **CO₂ emissions (g/km)**.

## Model

We use a **Random Forest Regressor** from Scikit-learn due to its robustness and performance on structured data. The model demonstrates high accuracy:

- **Mean Absolute Error (MAE)**: 2.55
- **Mean Squared Error (MSE)**: 135.46
- **R² Score**: 0.98

## Features Used

- `cylinders`: Number of engine cylinders
- `displ`: Engine displacement (L)
- `city`: Fuel consumption in city driving (L/100 km)
- `highway`: Fuel consumption on highway (L/100 km)
- `comb`: Combined fuel consumption (L/100 km)
- `feScore`: Fuel economy score
- `ghgScore`: Greenhouse gas score
- `year`: Model year

## Exploratory Analysis

- Strong **positive correlation**: `co2` vs `cylinders`, `displ`
- Strong **negative correlation**: `co2` vs `comb`, `city`, `feScore`, `ghgScore`
- Feature importance analysis reveals that **city fuel consumption** is the most important predictor of CO₂ emissions.

## Data Preprocessing

- Removed multicollinear features like `feScore` or `ghgScore` (high correlation).
- Converted categorical variables using **Label Encoding** or **One-Hot Encoding** as needed.
- Handled missing or invalid values to prepare the dataset for training.

## Requirements

To install required libraries:

in your terminal run this command: pip install -r requirements.txt
requirements.txt
numpy==1.24.0
pandas==1.5.3
matplotlib==3.6.3
seaborn==0.11.2
scikit-learn==1.1.3
🏁 How to Run

Ensure that the dataset CSV is present in your working directory or adjust the file path in your script.

Future Improvements
Hyperparameter tuning with GridSearchCV

Try other regressors (XGBoost, Gradient Boosting)

Model deployment using Flask or FastAPI

Integrate dashboard for real-time predictions
