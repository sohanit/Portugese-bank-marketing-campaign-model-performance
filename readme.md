# Portuguese Banking Institution Marketing Campaign Model Performance

## Project Description
The data is related to direct marketing campaigns (phone calls) of a Portuguese banking institution. The classification goal is to predict if the client will subscribe to a term deposit (variable y).

### Dataset Characteristics
- **Type**: Multivariate
- **Subject Area**: Business
- **Associated Tasks**: Classification
- **Feature Type**: Categorical, Integer
- **# Instances**: 45,211
- **# Features**: 16

### Goal
The goal is to compare the performance of the classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines) encountered in this section of the program.

## Usage Instructions
1. Open the Jupyter Notebook:
    ```sh
    jupyter notebook model-predictions.ipynb
    ```
2. Run the cells in the notebook to see the performance comparison of different classifiers.

## Dataset Overview

The dataset contains information from a Portuguese banking institution's marketing campaigns. It includes 41,188 records with 21 features, covering various aspects of the clients and the marketing interactions.

## Data Structure

The dataset has the following characteristics:

1. No missing values are present in any of the columns.
2. The features are a mix of numeric and categorical data types.

## Feature Analysis

### Numeric Features:
- age, duration, campaign, pdays, previous (integer type)
- emp.var.rate, cons.price.idx, cons.conf.idx, euribor3m, nr.employed (float type)

### Categorical Features:
- job, marital, education, default, housing, loan, contact, month, day_of_week, poutcome, y (object type)

## Potential Data Type Coercions

While most features seem appropriately categorized, some considerations for data type coercion include:

1. 'pdays': Currently an integer, but the value 999 represents "client not previously contacted." This could be transformed into a categorical variable or a boolean "previously_contacted" feature.

2. 'campaign': Although numeric, it might be beneficial to bin this into categories for analysis.

3. 'month' and 'day_of_week': These could be converted to datetime or ordinal types for time-based analysis.

4. 'y' (target variable): Could be encoded as a binary numeric type for modeling purposes.


## Objective

The Business Objective of this task is to predict whether a client will subscribe to a term deposit based on various client attributes and marketing campaign information. This prediction aims to help the Portuguese banking institution optimize its marketing efforts and improve the efficiency of its direct marketing campaigns.

Specifically, the objective involves:

1. Analyzing the provided dataset of previous marketing campaign results.
2. Developing predictive models using different classifiers (k-nearest neighbors, logistic regression, decision trees, and support vector machines).
3. Comparing the performance of these models to determine which one best predicts term deposit subscriptions.
4. Identifying key factors that influence a client's likelihood to subscribe to a term deposit.

By achieving this objective, the bank can:

- Target potential clients more effectively, focusing resources on those most likely to subscribe.
- Reduce costs associated with unsuccessful marketing attempts.
- Increase the success rate of their term deposit marketing campaigns.
- Gain insights into customer behavior and preferences related to term deposits.

Ultimately, this analysis will enable the bank to make data-driven decisions to enhance its marketing strategies and improve its overall business performance in promoting term deposits.


## Summary of Findings
The performance of the classifiers was evaluated based on various metrics. Here is a brief summary of the findings:

Baseline Performance Accuracy: 0.887556904400607
Linear Regression basic model findings:
    - **Accuracy: 0.9098
    - **Precision: 0.6644
    - **Recall: 0.4150
    - **F1-score: 0.5109

Optimized model performance comparisons:
- **K-Nearest Neighbors**:
    Best Parameters: {'n_neighbors': 7, 'weights': 'uniform'}
    Best CV Score: 0.5442
    Test Score: 0.5335
    Accuracy: 0.9098
    F1 Score: 0.5109
    Precision: 0.6644
    Recall: 0.4150

- **Logistic Regression**:
    Best Parameters: {'C': 10, 'solver': 'lbfgs'}
    Best CV Score: 0.5114
    Test Score: 0.5173
    Accuracy: 0.9098
    F1 Score: 0.5109
    Precision: 0.6644
    Recall: 0.4150

- **Decision Trees**:
    Best Parameters: {'max_depth': 7, 'min_samples_split': 2}
    Best CV Score: 0.5914
    Test Score: 0.5910
    Accuracy: 0.9098
    F1 Score: 0.5109
    Precision: 0.6644
    Recall: 0.4150

- **Support Vector Machines**:
    Best Parameters: {'C': 1, 'kernel': 'linear'}
    Best CV Score: 0.4765
    Test Score: 0.5024
    Accuracy: 0.9098
    F1 Score: 0.5109
    Precision: 0.6644
    Recall: 0.4150

For detailed results and analysis, please refer to the [Comparing-Performances.ipynb](http://_vscodecontentref_/0) notebook.

## Results:


| **Model**              | **Best Parameters**                  | **Best CV Score (F1)** | **Test Score (F1)** | **Accuracy** | **Precision** | **Recall** | **F1-Score** |
|-------------------------|---------------------------------------|-------------------------|----------------------|--------------|---------------|------------|--------------|
| **Logistic Regression** | `{'C': 10, 'solver': 'lbfgs'}`       | 0.5114                 | 0.5173               | 0.9098       | 0.6644        | 0.4150     | 0.5109       |
| **KNN**                | `{'n_neighbors': 7, 'weights': 'uniform'}` | 0.5442                 | 0.5335               | 0.9098       | 0.6644        | 0.4150     | 0.5109       |
| **Decision Tree**       | `{'max_depth': 7, 'min_samples_split': 2}` | 0.5914                 | 0.5910               | 0.9098       | 0.6644        | 0.4150     | 0.5109       |
| **SVM**                | `{'C': 1, 'kernel': 'linear'}`       | 0.4765                 | 0.5024               | 0.9098       | 0.6644        | 0.4150     | 0.5109       |

### **Notes on the Table:**
- **Best CV Score (F1):** Average F1-score from cross-validation during grid search.
- **Test Score (F1):** F1-score achieved on the test set after training with the best parameters.
- **Accuracy, Precision, Recall, and F1-Score:** Same values across models because predictions for the majority class (`y=0`) dominate due to imbalance in the dataset.


## Contribution Guidelines
If you would like to contribute to this project, please fork the repository and submit a pull request. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.