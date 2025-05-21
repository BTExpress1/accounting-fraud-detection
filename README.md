# Accounting Fraud Detection (2023)

**License:** MIT  
**Python Version:** 3.11  
**Last Updated:** May 2025  
📄 [View in NBViewer](https://nbviewer.org/github/BTExpress1/accounting-fraud-detection/blob/main/notebooks/)  

---

## 📘 Project Overview

This project applies machine learning techniques to detect accounting fraud using publicly available financial statement data. The objective is to identify suspicious patterns in corporate reporting and enable data-driven risk mitigation strategies for analysts, compliance teams, and regulators.

---

## 📂 Repository Structure & Notes

### Cookiecutter Template  
This repository follows the [cookiecutter data science](https://drivendata.github.io/cookiecutter-data-science/) layout. You may see standard directories (like `references/`, `docs/`, or `reports/`) that are either unused or minimally populated in this version. They are retained for structural consistency.

### Dataset & Origin  
The modeling is based on a structured dataset containing financial features from corporate filings. While the original dataset included additional engineered features and multiple sources, only the finalized and cleaned dataset is used in this repo for clarity.

## 📊 Dataset

The primary dataset was sourced from the [FraudDetection GitHub repository](https://github.com/JarFraud/FraudDetection), which accompanies a peer-reviewed paper published in the *Journal of Accounting Research*.

- 📁 **Dataset URL:** [data_FraudDetection_JAR2020.csv](https://raw.githubusercontent.com/JarFraud/FraudDetection/refs/heads/master/data_FraudDetection_JAR2020.csv)
- 📘 **Codebook:** [docs/codebook.md](https://github.com/BTExpress1/accounting-fraud-detection/blob/91c49a5ff1a04842bdc0ad81e0b3f0098035ed07/docs/codebook.md)

Several datasets were explored during the discovery phase. This dataset was ultimately selected for its high relevance, feature richness, and academic rigor.

If you use this dataset, please cite the original authors:

> Yang Bao, Bin Ke, Bin Li, Julia Yu, and Jie Zhang (2020).  
> *Detecting Accounting Fraud in Publicly Traded U.S. Firms Using a Machine Learning Approach*.  
> Journal of Accounting Research, 58(1): 199–235.  
> [Read the paper](https://onlinelibrary.wiley.com/doi/10.1111/1475-679X.12292)

## 📊 Dataset Selection Notes

A **considerable amount of time was spent selecting a suitable dataset**. Multiple public sources were evaluated before finalizing the financial fraud dataset published in the Journal of Accounting Research (JAR). The chosen dataset provides rich structured financial data with confirmed misstatement labels, enabling supervised learning for fraud detection.
---

## 🧠 Modeling Approach

### Baseline Modeling  
A CatBoost classifier was used as a high-performance baseline, selected for its native handling of class imbalance and minimal preprocessing needs. A deep neural network (DNN) was also implemented and tuned to improve generalization and sensitivity under rare-event conditions.

### Model Blending  
A final model was produced by blending the tuned CatBoost and DNN outputs using a weighted average. This ensemble approach delivered a favorable trade-off between precision and recall, essential for high-stakes fraud detection.

### Simulation-Based Interpretability  
Post-training, a perturbation analysis was conducted to simulate ±20% changes in key financial features. This enabled a nuanced understanding of how specific variables (e.g., retained earnings, payable index) impact fraud probability and offered explainability for audit teams.

---

## 💾 How to Use This Project

### Requirements
  
Python 3.13 is currently not supported by some libraries used in this project.

- Python 3.11  
- `pip`  
- Git Large File Storage (LFS)  
  ```bash
  git lfs install
  
### Installation
Clone the repository and install dependencies:
git clone https://github.com/BTExpress1/accounting-fraud-detection.git
cd accounting-fraud-detection
pip install -r requirements.txt

### 📁 Project Structure

├── data/                # Cleaned and transformed datasets (Git LFS)
├── models/              # Saved model artifacts (CatBoost, DNN, ensemble metadata)
├── notebooks/           # Jupyter notebooks (EDA, training, modeling)
├── reports/             # Final presentation and documentation
├── accountingfraud/     # Source code (modular scripts for config, training, plotting)
├── requirements.txt     # Python dependencies
└── README.md            # Project summary and usage guide

## ▶️ Running the Project
jupyter lab
Then open:

notebooks/fraud_Wrangling.ipynb

notebooks/fraud_EDA.ipynb

notebooks/fraud_preprocessing_and_training.ipynb

notebooks/fraud_modeling.ipynb

All outputs (models, plots, metadata) are saved to:

models/

reports/figures/

Note: Runtime may take ~2.5 hours for full execution due to hyperparameter tuning and model blending.

## 📌 Notes
Model artifacts and large files are versioned via Git LFS.

Python 3.11 is required due to TensorFlow, SciKeras, and CatBoost compatibility.

This repo reflects the final, clean version of the project. Earlier iterations and exploratory notebooks have been archived separately.

Notebook runtime includes DNN tuning (~50–60 min), CatBoost tuning (~7 min), and simulation analysis (~15–20 min).

📈 Future Enhancements
Add audit flags and qualitative disclosures (e.g., footnotes)

Incorporate board composition, auditor type, and litigation history

Deploy a dashboard or REST API for scenario testing and outreach targeting