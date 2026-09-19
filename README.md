# Bike Sharing Demand Prediction

A machine learning project that predicts the number of bike rentals using the UCI Bike Sharing Dataset.

## Dataset

The dataset contains hourly bike rental information along with features such as:

- Hour
- Temperature
- Humidity
- Windspeed
- Season
- Weather
- Weekday
- Working day
- Holiday

The target is `cnt`, which represents the total number of bike rentals.

## What I Did

- Cleaned the dataset
- Removed unnecessary and leaking features
- Explored relationships between features and bike demand
- Used one-hot encoding for categorical features
- Added `hr_squared` as a new feature
- Trained a Linear Regression model
- Trained a Random Forest Regressor
- Compared the models using MAE, RMSE, and R²
- Analyzed model residuals
- Tested limiting Random Forest tree depth and its effect on performance and model size
- Used the final model to make a real-world prediction

## Models

### Linear Regression

MAE: 96.51  
RMSE: 126.36  
R²: 0.496

### Random Forest

MAE: 24.90  
RMSE: 42.09  
R²: 0.944

Random Forest performed much better than Linear Regression because it can capture nonlinear relationships in the data.

### Limiting Tree Depth

The Random Forest was also tested with `max_depth=10`.

| Model | MAE | RMSE | R² | Model Size |
|---|---:|---:|---:|---:|
| Random Forest | 24.90 | 42.09 | 0.944 | ~114 MB |
| Random Forest (`max_depth=10`) | 31.74 | 50.89 | 0.918 | ~11 MB |

Limiting the tree depth reduced the model size significantly, but also slightly reduced its performance.

## Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
