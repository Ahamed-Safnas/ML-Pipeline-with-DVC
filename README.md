# ML Pipeline with DVC

## Project Overview

This project implements an **end-to-end machine learning pipeline** for **sentiment classification** using **DVC (Data Version Control)**.

The pipeline is fully automated and reproducible, covering:

* Data ingestion
* Text preprocessing
* Feature engineering
* Model training
* Model evaluation

Each step is tracked and versioned using DVC.

---

## Problem Statement

The goal is to classify tweets into:

* **Happiness (1)**
* **Sadness (0)**

The pipeline ensures that:

* Data changes are tracked
* Pipeline stages are reproducible
* Model results can be regenerated reliably

---

## Tech Stack

* Python
* scikit-learn
* NLTK
* Pandas, NumPy
* DVC

---

## Project Structure

```
ahamed-safnas-ml-pipeline-with-dvc/
│
├── src/
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   └── model_evaluation.py
│
├── data/
│   ├── raw/
│   ├── processed/
│   └── features/
│
├── model.pkl
├── metrics.json
├── dvc.yaml
├── dvc.lock
├── requirements.txt
└── README.md
```

---

## Pipeline Stages (DVC)

### 1. Data Ingestion

* Loads tweet emotion data from a public URL
* Filters relevant sentiments
* Splits data into train and test sets
* Stores raw data in `data/raw/`

### 2. Data Preprocessing

* Text normalization
* Stopword removal
* Lemmatization
* URL, number, and punctuation removal
* Outputs cleaned data to `data/processed/`

### 3. Feature Engineering

* Converts text to numerical features using **Bag of Words**
* Stores feature matrices in `data/features/`

### 4. Model Building

* Trains a **Gradient Boosting Classifier**
* Saves the trained model as `model.pkl`

### 5. Model Evaluation

* Evaluates the model using:

  * Accuracy
  * Precision
  * Recall
  * ROC-AUC
* Stores results in `metrics.json`

---

## Why DVC is Used

DVC is used to:

* Track data and model files
* Define pipeline stages
* Ensure reproducibility
* Automatically re-run only changed stages

Without DVC, managing data and pipeline dependencies becomes manual and error-prone.

---

## Setup Instructions

### 1. Clone the repository

```bash
git clone <repo-url>
cd ahamed-safnas-ml-pipeline-with-dvc
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate      # Linux / macOS
venv\Scripts\activate         # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

## Running the Pipeline

Run the entire pipeline using DVC:

```bash
dvc repro
```

DVC will:

* Execute stages in order
* Skip stages that have not changed
* Reproduce results consistently

---

## Outputs

* Trained model: `model.pkl`
* Evaluation metrics: `metrics.json`

---

## Key Learning Outcomes

* Building modular ML pipelines
* Versioning data and models
* Automating workflows with DVC
* Ensuring reproducibility in ML projects

---

## Notes

* This project is for learning and demonstration
* Not intended for production use
* Hyperparameter tuning is not included

---

## Author

Safnas

---

If you want next, I can:

* **Shorten this for a viva**
* **Add a pipeline diagram**
* **Rewrite it in resume-friendly language**
* **Integrate MLflow into this DVC pipeline**

Just say which one.
