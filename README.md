# NBA Shot Success Prediction

This repository contains a project that predicts NBA shot success using advanced shot metrics. The project leverages several machine learning models (Logistic Regression, SVM, Artificial Neural Networks, XGBoost, and LightGBM) to analyze and predict the likelihood of a successful shot based on contextual game factors and engineered features.

## Table of Contents

- [About the Project](#about-the-project)
- [Acknowledgements](#acknowledgements)
- [Environment Setup](#environment-setup)
- [Data Documentation](#data-documentation)

## About the Project

In modern NBA analytics, predicting the success of a shot can provide valuable insights for teams and coaches. This project:
- Utilizes a dataset comprising shot data from the NBA 2021–2024 seasons.
- Extracts and engineers features such as shot distance, player location, shot type, defender proximity, relative shot difficulty, and congestion proxy.
- Implements multiple machine learning algorithms to benchmark performance and draw insights.
- Evaluates models based on accuracy, precision, recall, F1-score, and ROC-AUC.

For further details, please refer to the [final project report](Predicting NBA Player Shooting Success Using Advanced Shot Metrics.pdf).

## Acknowledgements
## Acknowledgments

This project was completed as a team effort alongside:
- Adithya Hari (worked on feature engineering, Logistic Regression and SVM)
- Quianyi Zhang (worked on data preprocessing, neural network model)
- Anandha Ragavean Ravi (worked on XGBoost and LightGBM models)

My contributions focused on the Logistic Regression and SVM portions of the project.

Please note that this repository only includes my personal contributions for demonstration purposes.

## Environment Setup

To run the project, the following setup and instructions are provided:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/nba-shot-success-prediction.git
   cd nba-shot-success-prediction
2. pip install -r requirements.txt
3. jupyter notebook NBA_Shot_Success.ipynb

## Data Documentation
## Data Source

This project uses the [NBA Shots Dataset](https://www.kaggle.com/datasets/mexwell/nba-shots?resource=download) from Kaggle, which contains NBA data spanning the 2004 to 2024 seasons. For the scope of this project, the data from the 2021 season till the 2024 season has been used. Please refer to the dataset page for more details and licensing information.

For further information on the data used in this dataset, refer to the DATA_DESCRIPTION.md file.