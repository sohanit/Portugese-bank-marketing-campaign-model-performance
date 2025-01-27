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

- Baseline Performance Accuracy: 0.887556904400607
  
- Linear Regression basic model findings:
  - Accuracy: 0.9098
  - Precision: 0.6644
  - Recall: 0.4150
  - F1-score: 0.5109

Optimized model performance comparisons:


| **Model**              | **Best Parameters**                  | **Best CV Score** | **Test Score** | **Accuracy** | **F1 Score** | **Precision** | **Recall** |
|-------------------------|---------------------------------------|-------------------|----------------|--------------|--------------|---------------|------------|
| Logistic Regression     | {'C': 1, 'solver': 'saga'}          | 0.5126            | 0.2039         | 0.9114       | 0.5247       | 0.6705        | 0.4310     |
| KNN                     | {'n_neighbors': 3, 'weights': 'distance'} | 0.4200            | 0.2050         | 0.8920       | 0.4410       | 0.5342        | 0.3754     |
| Decision Tree           | {'max_depth': 3, 'min_samples_split': 2} | 0.5881            | 0.2039         | 0.9090       | 0.5959       | 0.6004        | 0.5914     |
| SVM                     | {'C': 10, 'kernel': 'rbf'}          | 0.5057            | 0.0000         | 0.9084       | 0.5525       | 0.6197        | 0.4984     |


### Summary of Model Performance:

1. **Logistic Regression**:
   - Achieved the **highest accuracy** (91.14%) and performed relatively well across metrics.
   - The **best F1 score** was 0.5247, with good precision (0.6705) but a lower recall (0.4310).
   - Tuned with parameters `C=1` and `solver='saga'`.

2. **KNN (K-Nearest Neighbors)**:
   - Showed the **lowest performance overall**, with an accuracy of 89.20% and an F1 score of 0.4410.
   - Precision (0.5342) and recall (0.3754) were weaker compared to other models.
   - Optimal parameters were `n_neighbors=3` and `weights='distance'`.

3. **Decision Tree**:
   - Performed reasonably well, achieving an F1 score of 0.5959, **highest recall** (0.5914), and good precision (0.6004).
   - Accuracy was 90.90%, slightly lower than Logistic Regression.
   - Best parameters were `max_depth=3` and `min_samples_split=2`.

4. **SVM (Support Vector Machine)**:
   - Demonstrated moderate performance, with an accuracy of 90.84% and an F1 score of 0.5525.
   - Precision (0.6197) was good, but recall (0.4984) lagged slightly.
   - Best parameters were `C=10` and `kernel='rbf'`.

### Key Observations:
- Logistic Regression and Decision Tree models emerged as strong performers for this dataset.
- KNN lagged behind significantly in overall performance, particularly in recall and F1 scores.
- SVM showed balanced performance but did not surpass the Decision Tree or Logistic Regression in key metrics.

For detailed results and analysis, please refer to the [model-predictions.ipynb](https://github.com/sohanit/Portugese-bank-marketing-campaign-model-performance/blob/main/model-predictions.ipynb) notebook.

## Contribution Guidelines
If you would like to contribute to this project, please fork the repository and submit a pull request. For major changes, please open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.