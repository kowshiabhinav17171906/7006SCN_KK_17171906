```markdown
# 7006SCN Machine Learning and Big Data

# HIGGS Signal Prediction using PySpark

**Name:** Kowshiabhinav Konda  
**SID:** 17171906  
**Module:** Machine Learning and Big Data  
**Module Code:** 7006SCN  
**Submission Date:** 29/06/2026  

---

## Project Overview

This project develops a distributed machine learning pipeline using PySpark to classify whether a particle collision event represents a HIGGS boson signal or background noise. The complete workflow includes data engineering, feature preprocessing, model development, distributed computing, model evaluation, stability analysis, and Tableau dashboard visualization.

---

## Dataset

- **Source:** https://archive.ics.uci.edu/dataset/280/higgs
- **Dataset:** HIGGS Dataset
- **Size:** 11 million rows and 29 columns
- **Problem Type:** Binary Classification
- **Target Variable:** Class (1 = HIGGS Signal, 0 = Background)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

---

## Repository Structure

```

Notebooks/
│── Task1 Notebook.ipynb    # Problem Understanding and Dataset Exploration
│── Task2 Notebook.ipynb    # Data Engineering
│── Task3 Notebook.ipynb    # Machine Learning Model Development
│── Task4 Notebook.ipynb    # Distributed Computing
│── Task5 Notebook.ipynb    # Model Evaluation and Stability
│── Task6 Notebook.ipynb    # Tableau Storytelling

```

---

## Machine Learning Models

The following PySpark MLlib classification algorithms were implemented:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosted Trees (GBT)

---

## Feature Engineering

- Missing value handling
- Feature Vector Assembly
- StandardScaler for feature scaling
- Train/Test Split
- Pipeline implementation using PySpark ML Pipeline

---

## Distributed Computing

- Apache Spark (PySpark)
- Distributed data processing
- Data caching and persistence
- Spark execution analysis using Spark UI

---

## Results

The performance of different machine learning models was evaluated using Accuracy, Precision, Recall, F1-Score, and AUC-ROC.

Gradient Boosted Trees (GBT) achieved the highest overall performance, followed closely by Random Forest. Feature importance analysis identified **C26** and **C28** as the most influential features for predicting HIGGS signals.

---

## Tableau Dashboard

The project includes interactive Tableau dashboards for:

- Dataset Overview
- Model Performance Comparison
- Prediction Confidence
- Feature Importance
- Scalability and Cost Analysis

---

## Tableau Public URL

https://public.tableau.com/app/profile/kowshiabhinav.konda/vizzes

---

## Technologies Used

- Python
- PySpark
- Apache Spark
- Pandas
- Matplotlib
- Tableau Public

---

## Author

**Kowshiabhinav Konda**  
SID: 17171906
```
