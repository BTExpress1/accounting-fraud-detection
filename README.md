
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

To establish a performance benchmark, a simple logistic regression model was applied using scaled features. No feature selection or hyperparameter tuning was performed. This baseline helped in understanding the data's predictive capacity before employing more complex models.

### Advanced Modeling

Recognizing the limitations of linear models in capturing complex patterns, advanced tree-based models like Random Forest and LightGBM were implemented. These models demonstrated improved performance in detecting fraudulent activities.

### Modeling Refinement

During model development, significant overfitting was observed, driven by features strongly correlated with the target variable. To address this, several high-weight, redundant, or skewed features were removed to reduce bias and improve generalization. The final model emphasizes financial ratios and accounting metrics that are more indicative of fraudulent behavior.

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
