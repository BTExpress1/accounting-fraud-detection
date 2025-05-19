
# Accounting Fraud Detection

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Status](https://img.shields.io/badge/status-in--progress-yellow)
![Python](https://img.shields.io/badge/python-3.11%20or%20lower-critical)

> ⚠️ This project **requires Python ≤ 3.11**. It is **not compatible with Python 3.12 or 3.13+** due to current incompatibilities with both `CatBoost` and `TensorFlow`.

## Overview

## 🚀 Project Progress Overview

As of this stage, the project has successfully completed:

- ✅ Structured and domain-aware data wrangling
- ✅ Fast, high-signal exploratory data analysis (EDA)
- ✅ Clean and strategy-driven feature scaling
- ✅ Train/test split with target stratification
- ✅ Three baseline models trained and evaluated:
  - Random Forest (bagging)
  - CatBoostClassifier (boosting)
  - Deep Neural Network (DNN)

We intentionally avoided linear models due to the nonlinear and correlated nature of financial features.

## Problem Statement

## 🧪 Requirements Update

> ⚠️ This project **requires Python 3.11** due to compatibility with:
- `CatBoost`
- `TensorFlow`  
Python 3.13 is currently not supported by these libraries.

## Dataset
The primary dataset was sourced from the [FraudDetection GitHub repository](https://github.com/JarFraud/FraudDetection), which accompanies a peer-reviewed paper published in the *Journal of Accounting Research*.

- Dataset URL: [data_FraudDetection_JAR2020.csv](https://raw.githubusercontent.com/JarFraud/FraudDetection/refs/heads/master/data_FraudDetection_JAR2020.csv)

For detailed descriptions of all raw and engineered variables, refer to the [codebook](https://github.com/BTExpress1/accounting-fraud-detection/blob/91c49a5ff1a04842bdc0ad81e0b3f0098035ed07/docs/codebook.md).

Several datasets were explored during the discovery phase. This dataset was selected for its high relevance, feature richness, and grounding in academic research.

If you use this dataset, please cite the original authors:

Yang Bao, Bin Ke, Bin Li, Julia Yu, and Jie Zhang (2020). [Detecting Accounting Fraud in Publicly Traded U.S. Firms Using a Machine Learning Approach](https://onlinelibrary.wiley.com/doi/10.1111/1475-679X.12292). Journal of Accounting Research, 58 (1): 199–235.

## 📊 Dataset Selection Notes

A **considerable amount of time was spent selecting a suitable dataset**. Multiple public sources were evaluated before finalizing the financial fraud dataset published in the Journal of Accounting Research (JAR). The chosen dataset provides rich structured financial data with confirmed misstatement labels, enabling supervised learning for fraud detection.

## Project Structure

## 📁 Current Files Generated

- `fraud_data_eda.csv`: Cleaned and imputed data post-wrangling and EDA
- `notebooks/01_data_wrangling.ipynb`: Imputation, outlier handling, and codebook creation
- `notebooks/02_eda.ipynb`: Distribution analysis, correlation heatmaps, scaling decisions
- `notebooks/03_preprocessing_and_training.ipynb`: Model-ready preprocessing and baseline training

## How to Run

## Results

## Future Work

## Author

Bini Teklehaimanot
