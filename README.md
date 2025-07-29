
# 🧾 Accounting Fraud Detection (2023)

![Python](https://img.shields.io/badge/python-3.11-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Git LFS](https://img.shields.io/badge/Git-LFS-critical)
[![View in NBViewer](https://img.shields.io/badge/view%20in-NBViewer-orange)](https://nbviewer.org/github/BTExpress1/accounting-fraud-detection/tree/main/notebooks/)

## 📚 Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Dataset](#dataset)
- [Modeling Approach](#modeling-approach)
- [Usage Instructions](#usage-instructions)
- [License](#license)

## 📌 Project Overview

This repository presents a data science project focused on detecting accounting fraud in publicly traded U.S. firms. The goal is to identify fraudulent financial reporting using machine learning techniques, providing actionable insights for auditors, regulators, and stakeholders.

## 🗂️ Repository Structure

```
.
├── data/               # Raw and processed datasets
├── docs/               # Documentation and codebook
├── models/             # Trained model artifacts
├── notebooks/          # Jupyter notebooks for EDA, training, and modeling
├── reports/            # Final reports and figures
├── accounting_fraud/   # Source code for data processing and modeling
├── requirements.txt    # Python dependencies
└── README.md           # Project overview and instructions
```

*Note: This repository was scaffolded using the [cookiecutter data science template](https://drivendata.github.io/cookiecutter-data-science/). Some folders may contain placeholder files.*

## 📊 Dataset

The primary dataset was sourced from the [FraudDetection GitHub repository](https://github.com/JarFraud/FraudDetection), which accompanies a peer-reviewed paper published in the *Journal of Accounting Research*.

- **Dataset URL**: [data_FraudDetection_JAR2020.csv](https://raw.githubusercontent.com/JarFraud/FraudDetection/refs/heads/master/data_FraudDetection_JAR2020.csv)
- **Codebook**: [docs/codebook.md](https://github.com/BTExpress1/accounting-fraud-detection/blob/main/docs/codebook.md)

A **considerable amount of time was spent selecting a suitable dataset**. Multiple public sources were evaluated before finalizing the financial fraud dataset published in the *Journal of Accounting Research (JAR)*. The chosen dataset provides rich structured financial data with confirmed misstatement labels, enabling supervised learning for fraud detection.

If you use this dataset, please cite the original authors:

> Yang Bao, Bin Ke, Bin Li, Julia Yu, and Jie Zhang (2020).  
> *Detecting Accounting Fraud in Publicly Traded U.S. Firms Using a Machine Learning Approach*.  
> Journal of Accounting Research, 58(1): 199–235.  
> [Read the paper](https://onlinelibrary.wiley.com/doi/10.1111/1475-679X.12292)

## 🤖 Modeling Approach

### Baseline Modeling

A Random Forest model was used as the baseline to gauge the dataset’s predictive capacity without heavy tuning. This provided an early benchmark and highlighted the severe class imbalance challenge — fraud cases were <1% of observations.

### Advanced Modeling

To improve recall and handle the imbalance more effectively, we moved to CatBoost, which excelled with categorical handling and delivered strong baseline ROC-AUC performance. A Deep Neural Network (DNN) was then introduced to capture nonlinear relationships.

A blended ensemble (80% CatBoost / 20% DNN) was created, tuned via GridSearch to optimize fraud recall while maintaining business-usable precision.

### Threshold & Interpretability Enhancements

- KS-based thresholding: Kolmogorov–Smirnov statistics were used to set and simulate thresholds for different “top N” review scenarios (e.g., top 1K, 3K, 5K cases).
- SHAP interpretability: Added SHAP value analysis to provide local and global explanations for fraud flags, giving compliance teams insight into why a record was flagged.

### Modeling Refinement

Overfitting was reduced by removing highly correlated or redundant features. The final model focuses on interpretable financial ratios (e.g., Days Payable Index, Retained Earnings changes) that auditors can understand and trace.

## 🚀 Usage Instructions

### Requirements

- Python 3.11
- pip
- Git LFS (for downloading large model and data files)

Python 3.13 is currently not supported by some libraries used in this project.

### Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/BTExpress1/accounting-fraud-detection.git
cd accounting-fraud-detection
pip install -r requirements.txt
```

Initialize Git LFS:

```bash
git lfs install
```

### Running the Project

Launch Jupyter Lab or Notebook:

```bash
jupyter lab
```

Open and run the following notebooks in order:

1. `notebooks/01_data_wrangling.ipynb`
2. `notebooks/02_eda.ipynb`
3. `notebooks/03_preprocessing_and_training.ipynb`
4. `notebooks/04_modeling.ipynb`

Results, models, and charts will be saved automatically to:

- `models/`
- `reports/figures/`

> ⏱️ Full modeling notebook runtime (end-to-end): **3,783.43 seconds (~63 minutes)**

## 📄 License

This project is licensed under the MIT License.
