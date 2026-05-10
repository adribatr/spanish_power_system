# Electricity demand and price forecasting in the spanish power system

## Project overview

This Master's Thesis focuses on the prediction of electricity demand and electricity market prices in the Spanish power system using Machine Learning techniques and publicly available energy market data.

The project combines hourly data obtained from Red Eléctrica de España (REE) and Operador del Mercado Ibérico de Energía (OMIE), to build a complete dataset containing electricity demand, market prices, generation mix, storage variables, and international electricity exchanges.

The workflow covers:
- Data acquisition
- Preprocessing
- Exploratory analysis
- Feature engineering
- Predictive modeling
- Hyperparameter tuning
- Model evaluation

# Repository Structure

---
## [/data/](./data/)

Main directory containing all datasets used throughout the project.

### [/data/raw_data/](./data/raw_data/)

Contains the original downloaded datasets.

#### [/data/raw_data/csv/](./data/raw_data/csv/)

CSV files obtained from OMIE.

#### [/data/raw_data/json/](./data/raw_data/json/)

JSON files downloaded from the REE API.

### [/data/preprocessed_data/](./data/preprocessed_data/)

Apache Parquet file containing the cleaned and merged dataset generated after preprocessing.



### [/data/model_data/](./data/model_data/)

Apache Parquet file containing the final dataset used for Machine Learning modeling.

---

## [notebooks/](./notebooks/)

Contains the complete end-to-end workflow divided into sequential Jupyter notebooks.

### `01_get_data.ipynb`

Downloads and consolidates raw data from REE and OMIE.

---

### `02_preprocess_data.ipynb`

Performs:
- Data cleaning
- Datetime processing
- Dataset merging
- Missing value handling

---

### `03_exploratory_data_analysis.ipynb`

Exploratory analysis focused on:
- Descriptive analysis
- Temporal evolution
- Seasonality
- Correlations

---

### `04_feature_engineering.ipynb`

Generation of modeling variables such as:
- Cyclical temporal variables
- Lag features
- Rolling statistics
- Energy system indicators

---

### `05_model_training.ipynb`

Machine Learning modeling and evaluation:
- Baseline forecasting
- Linear Regression
- Random Forest
- XGBoost
- Hyperparameter tuning
- Model comparison

---

## [html/](./html/)

Contains exported HTML versions of the notebooks.

---

## `requirements.txt`

Python dependencies required to reproduce the project environment.

---

# Installation

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Additional dependency for OMIE data extraction:

```bash
python -m pip install OMIEData
```

---

# Methodology

The project follows a complete Machine Learning pipeline for time-series forecasting.

The final dataset combines temporal information, historical demand and price behavior, energy generation variables, and electricity exchange indicators.

Several regression models are trained and compared using standard forecasting metrics such as  MAE, RMSE and R².

A naïve persistence baseline is also included for comparison.

---

# Key Findings

- Machine Learning models significantly outperform naïve baseline forecasting.
- Temporal lag variables provide the strongest predictive signal.
- XGBoost achieved the best overall performance after hyperparameter tuning.
- Electricity demand is more stable and predictable than electricity market prices.
- Energy generation and international exchanges improve predictive performance, especially for price forecasting.

---

# Author
**Adrián Barrios Trujillo** 

Master in Data Science

Universitat Oberta de Catalunya (UOC) - 2026