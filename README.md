# Distributed HIGGS Signal Prediction - Big Data Classification Project

## Research Question

Can particle collision events be accurately classified as HIGGS boson signals or background noise at big-data scale using a fully distributed PySpark machine learning pipeline?

## Business Framing

The HIGGS dataset contains simulated particle collision events collected to distinguish HIGGS boson signals from background processes. The binary classification task predicts whether an event represents a HIGGS signal based on 28 physical features extracted from detector measurements. Accurate classification supports high-energy physics research by reducing manual analysis, improving event selection, and demonstrating how distributed machine learning can efficiently process extremely large scientific datasets.

## Dataset

* **Source:** UCI Machine Learning Repository – HIGGS Dataset
* **File:** `HIGGS.csv`
* **Scale:** 11,000,000 rows and 29 columns.
* **Target:** `label` (Binary classification: 1 = HIGGS signal, 0 = background).
* **License:** Creative Commons Attribution 4.0 International (CC BY 4.0).
* **SparkSession (Task 4 run):** Local mode using PySpark with distributed processing on CPU.

## Algorithms

| Algorithm                    | Library       | Environment | Purpose                                       |
| ---------------------------- | ------------- | ----------- | --------------------------------------------- |
| Logistic Regression          | PySpark MLlib | CPU         | Linear baseline classifier                    |
| Decision Tree Classifier     | PySpark MLlib | CPU         | Interpretable tree-based classifier           |
| Random Forest Classifier     | PySpark MLlib | CPU         | Ensemble learning using bagged decision trees |
| Gradient Boosted Trees (GBT) | PySpark MLlib | CPU         | Boosted ensemble classifier                   |

All models are trained using PySpark MLlib and evaluated using standard classification metrics. The complete workflow runs on CPU without GPU dependency.

## Feature Engineering

* **Input features:** 28 numerical physics measurements describing each collision event.
* **Missing values:** Checked and handled during preprocessing.
* **Scaling:** StandardScaler applied to normalize feature values.
* **Transformation:** VectorAssembler combines all numerical features into a single `features` vector.
* **Train/Test Split:** Dataset divided into training and testing sets using an 80/20 random split with a fixed random seed for reproducibility.

All preprocessing stages are implemented within a PySpark Pipeline to ensure consistent transformations and prevent data leakage.

## Project Structure

```text
HIGGS/
|-- notebooks/
|   |-- Task1_Problem_and_Dataset.ipynb
|   |-- Task2_Data_Engineering.ipynb
|   |-- Task3_ML_Model_Portfolio.ipynb
|   |-- Task4_Distributed_Computing.ipynb
|   |-- Task5_Model_Evaluation_and_Stability.ipynb
|   |-- Task6_Tableau_Storytelling.ipynb
|
|-- output/
|   |-- figures/
|   |-- *.csv
|
README.md
```

## Execution Environment

* **Engine:** Apache Spark (PySpark)
* **Compute:** CPU only (Spark MLlib)
* **Programming Language:** Python
* **Development Environment:** Jupyter Notebook

## Sampling Strategy

The HIGGS dataset contains approximately 11 million observations. The data is randomly split into 80% training data and 20% testing data using a fixed random seed to ensure reproducibility. The testing dataset remains unseen during model training and is used exclusively for evaluating model performance.

## Quick Start

Install PySpark together with pandas, matplotlib, and scikit-learn. Download the HIGGS dataset from the UCI Machine Learning Repository and place it locally before executing the notebooks in order.

```bash
jupyter nbconvert --to notebook --execute notebooks/Task1_Problem_and_Dataset.ipynb
jupyter nbconvert --to notebook --execute notebooks/Task2_Data_Engineering.ipynb
jupyter nbconvert --to notebook --execute notebooks/Task3_ML_Model_Portfolio.ipynb
jupyter nbconvert --to notebook --execute notebooks/Task4_Distributed_Computing.ipynb
jupyter nbconvert --to notebook --execute notebooks/Task5_Model_Evaluation_and_Stability.ipynb
jupyter nbconvert --to notebook --execute notebooks/Task6_Tableau_Storytelling.ipynb
```

## Pipeline (Run Notebooks in Order)

* **Task 1** – Introduce the problem, load the HIGGS dataset, inspect the schema, and discuss dataset characteristics.
* **Task 2** – Perform data preprocessing, feature scaling, feature assembly, and create the PySpark pipeline.
* **Task 3** – Train Logistic Regression, Decision Tree, Random Forest, and Gradient Boosted Tree classifiers.
* **Task 4** – Demonstrate distributed computing concepts including caching, persistence, partitioning, and Spark UI analysis.
* **Task 5** – Evaluate model performance using Accuracy, Precision, Recall, F1-score, ROC-AUC, PR curves, confusion matrices, and feature importance.
* **Task 6** – Export processed datasets and model results for Tableau dashboard development.

## Key Hyperparameters

* **Logistic Regression:** Regularization and maximum iterations.
* **Decision Tree:** Maximum depth and maximum bins.
* **Random Forest:** Number of trees and maximum depth.
* **Gradient Boosted Trees:** Maximum iterations and tree depth.

## Model Results

| Model                  |        Accuracy |  Precision      |   F1 Score      |    ROC-AUC   |
| ---------------------- | --------------: | --------------: | --------------: | --------------: 
| Logistic Regression    | *(0.635175)*    | *(0.635862)*    | *(0.629832)*    | *(0.679043)* 
| Decision Tree          | *(0.704703)*    | *(0.704703)*    | *(0.704703)*    | *(0.669855)* 
| Random Forest          | *(0.697418)*    | *(0.697084)*    | *(0.696473)*    | *(0.769555)* 
| Gradient Boosted Trees | *(0.718196)*    | *(0.718026)*    | *(0.718085)*    | *(0.795335)* 
Gradient Boosted Trees achieved the highest overall classification performance across the evaluation metrics, followed closely by Random Forest. Logistic Regression provided a strong linear baseline, while Decision Tree offered greater interpretability with comparatively lower predictive performance.

## Output Artifacts

* `output/figures/` – Dataset distribution, feature importance, ROC curves, Precision-Recall curves, confusion matrices, model comparison charts, and prediction confidence visualizations.
* Exported CSV files for Tableau dashboards including:

  * `model_metrics.csv`
  * `feature_importance.csv`
  * `prediction_confidence.csv`
  * `scalability_results.csv`
  * `cost_analysis.csv`

## Tableau Public

https://public.tableau.com/app/profile/kowshiabhinav.konda/vizzes

## Version Information

| Component      | Version |
| -------------- | ------- |
| PySpark        | 4.x     |
| Python         | 3.x     |
| pandas         | Latest  |
| scikit-learn   | Latest  |
| Tableau Public | Latest  |
