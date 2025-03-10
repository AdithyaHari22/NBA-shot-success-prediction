# Data Description: NBA Shots Dataset

## Overview

This document provides a comprehensive description of the NBA Shots dataset used for predicting shot success in NBA games. The dataset was sourced from [Kaggle](https://www.kaggle.com/datasets/mexwell/nba-shots?resource=download&select=NBA_2024_Shots.csv) and covers data from the **2021 to 2024 NBA seasons**. Originally, the dataset contained approximately 20 features and over 27,000 rows. After extensive preprocessing and feature selection, the final working dataset includes 14 key features used for modeling.

## Data Source

- **Dataset URL:** [NBA Shots Dataset on Kaggle](https://www.kaggle.com/datasets/mexwell/nba-shots?resource=download&select=NBA_2024_Shots.csv)
- **Time Period Covered:** 2021–2024 NBA seasons
- **Original Format:** CSV file
- **Usage License:** Please refer to the dataset’s Kaggle page for licensing and attribution details.

## Feature Descriptions

Below is a description of the key features included in the final dataset:

### Numerical Features

- **SHOT_DISTANCE:**  
  The distance (in feet) from the basket where the shot was attempted. This is a crucial factor affecting shot difficulty.

- **LOC_X & LOC_Y:**  
  The X and Y coordinates representing the player’s position on the court at the time of the shot. These features are used to map shot locations and understand spatial shot distribution.

- **CONGESTION_PROXY:**  
  An engineered feature representing the level of defensive congestion around the shooter. Higher congestion typically correlates with a lower probability of shot success.

- **RELATIVE_SHOT_DIFFICULTY:**  
  An engineered measure combining shot distance, defensive pressure, and shot type to quantify the overall difficulty of the shot.

### Categorical Features

- **SHOT_TYPE:**  
  The classification of the shot (e.g., jump shot, layup). Different shot types may have inherently different success rates.

- **BASIC_ZONE:**  
  A broad categorization of the area on the court where the shot was taken (e.g., above the break, restricted area).

- **ZONE_RANGE:**  
  Further categorizes the shot distance (e.g., short, mid, long). This helps in understanding performance variations over different ranges.

### Target Variable

- **SHOT_MADE:**  
  A binary indicator where:
  - `1` represents a successful shot.
  - `0` represents a missed shot.

## Data Preprocessing

To prepare the dataset for machine learning, the following preprocessing steps were applied:

- **Handling Missing Values:**  
  - Numerical features were filled using the median to minimize skew.
  - Categorical features were imputed with the mode of their respective columns.

- **Outlier Removal:**  
  Outliers, such as unrealistic shot distances, were removed using the Interquartile Range (IQR) method.

- **Feature Engineering:**  
The following features were engineered and addeed to the dataset to provide more context to the data as well see how various factors had an effect on if a SHOT was 'MADE' or 'MISSED':
**1. TIME_REMAINING_QUARTER**:
**2. CONGESTION_PROXY**:
**3. RELATIVE_SHOT_DIFFICULTY**:
**4. SHOT_CONGESTION**:
**5. IS_CLUTCH**:

- **Encoding and Normalization:**  
  - Categorical variables like `SHOT_TYPE` and `ZONE_RANGE` were transformed using one-hot encoding.
  - Numerical features such as `SHOT_DISTANCE`, `LOC_X`, and `LOC_Y` were normalized (e.g., using Z-score normalization) to ensure uniform scaling across features.

- **Addressing Class Imbalance:**  
  The target variable (`SHOT_MADE`) is imbalanced, with more missed shots than made ones. Techniques like SMOTE were applied during model training to help balance the class distribution.

## Data Quality and Limitations

- **Class Imbalance:**  
  The imbalance between successful and missed shots is significant. This is a common challenge in sports analytics and requires careful handling during model training.

- **Measurement Noise:**  
  As with many sports datasets, there may be noise or errors in shot tracking data. Rigorous preprocessing helps mitigate some of these issues.

- **Feature Reduction:**  
  Although the original dataset had around 20 features, only 14 were selected after preprocessing. Additional variables may exist that were not included in the final model due to redundancy or lack of predictive power.

## Usage in the Project

This dataset is used to train and evaluate various machine learning models (such as Logistic Regression, SVM) to predict the success of NBA shots. The engineered features, along with the raw shot metrics, form the basis for understanding the factors influencing shot success.

## Attribution

Please cite the original dataset if you use it in your work. A suggested citation format is:

> *NBA Shots Dataset. Kaggle. Available at: [https://www.kaggle.com/datasets/mexwell/nba-shots?resource=download&select=NBA_2024_Shots.csv](https://www.kaggle.com/datasets/mexwell/nba-shots?resource=download&select=NBA_2024_Shots.csv).*

For additional details and further reading, please refer to the [final project report](Predicting NBA Player Shooting Success Using Advanced Shot Metrics.pdf).

