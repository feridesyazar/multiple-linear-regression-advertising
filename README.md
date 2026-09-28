# Multiple Linear Regression – Advertising Sales Prediction

## Overview

This project uses **Multiple Linear Regression** to analyze the relationship between advertising spending and Sales.

The dataset contains advertising spending for:

- TV
- Radio
- Newspaper

The target variable is:

- Sales

The main objective is to understand how Sales changes when advertising spending increases and to identify which advertising channel has the strongest estimated effect.

---

## Business Objective

The project answers three main questions:

1. How much does Sales change when investment in each advertising channel increases?
2. Which advertising channel has the strongest estimated effect on Sales?
3. How close are the predicted Sales values to the actual Sales values in the test dataset?

This is a **regression problem**, where:

```python
x = df[["TV", "Radio", "Newspaper"]]
y = df["Sales"]
```

---

## Project Workflow

```text
Advertising Dataset
        ↓
Exploratory Data Analysis
        ↓
Correlation Analysis
        ↓
Feature and Target Selection
        ↓
Train-Test Split
        ↓
Multiple Linear Regression
        ↓
Regression Coefficients
        ↓
Model Evaluation
        ↓
Actual vs Predicted Sales
        ↓
Business Interpretation
```

---

## Exploratory Data Analysis

The dataset was examined using:

- Dataset structure and data types
- Missing value analysis
- Duplicate row check
- Descriptive statistics
- Correlation matrix
- Scatter plots for:
  - TV vs Sales
  - Radio vs Sales
  - Newspaper vs Sales

These analyses provide an initial view of the relationships between advertising spending and Sales.

---

## Multiple Linear Regression

A Multiple Linear Regression model was trained using:

- TV
- Radio
- Newspaper

as predictor variables and:

- Sales

as the target variable.

The dataset was divided into training and test sets using an **80/20 split**.

---

## Regression Equation

The fitted regression equation is approximately:

```text
Sales = 2.9791
        + 0.0447 × TV
        + 0.1892 × Radio
        + 0.0028 × Newspaper
```

Holding the other variables constant:

- A one-unit increase in **TV** advertising is associated with approximately **0.0447 additional Sales units**.
- A one-unit increase in **Radio** advertising is associated with approximately **0.1892 additional Sales units**.
- A one-unit increase in **Newspaper** advertising is associated with approximately **0.0028 additional Sales units**.

### Advertising Channel Effects

| Advertising Channel | Coefficient |
| --- | ---: |
| Radio | 0.1892 |
| TV | 0.0447 |
| Newspaper | 0.0028 |

**Radio has the highest regression coefficient and therefore the strongest estimated effect per unit of advertising spending in this model.**

---

## Model Evaluation

The model was evaluated using three regression metrics:

| Metric | Result |
| --- | ---: |
| MAE | 1.4608 |
| RMSE | 1.7816 |
| R² | 0.8994 |

### Interpretation

**MAE – Mean Absolute Error**

The predictions differ from the actual Sales values by approximately **1.46 Sales units on average**.

Lower MAE values indicate smaller prediction errors.

**RMSE – Root Mean Squared Error**

The RMSE is approximately **1.78 Sales units**.

RMSE gives more weight to larger prediction errors. Lower values are better.

**R² – Coefficient of Determination**

The R² score is **0.8994**.

This means that the model explains approximately **89.94% of the variation in Sales** in the test data.

---

## Actual vs Predicted Sales

The actual Sales values from the test dataset and the predicted Sales values are visualized together using a **line chart**.

This makes it possible to visually compare the model predictions with the real Sales values.

---

## Key Findings

The analysis shows that:

- **Radio** has the strongest estimated effect per unit of advertising spending.
- **TV** also has a positive relationship with Sales.
- **Newspaper** has only a very small estimated effect in the fitted model.
- The model achieves an **R² of 0.8994**, indicating a strong fit for this dataset.
- The actual and predicted Sales values can be compared directly using the test-set line chart.

---

## Technologies

- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Repository Structure

```text
multiple-linear-regression-advertising/
│
├── multiple_linear_regression.ipynb
├── advertising.csv
└── README.md
```

---

## Conclusion

This project demonstrates how **Multiple Linear Regression** can be used to analyze the relationship between advertising spending and Sales.

The regression coefficients provide an estimate of how much Sales changes when spending in each advertising channel increases while the other variables are held constant.

Among the three advertising channels, **Radio has the highest estimated effect per unit of spending**, followed by TV, while Newspaper has the smallest estimated effect.

The model achieved:

- **MAE:** 1.4608
- **RMSE:** 1.7816
- **R²:** 0.8994

Overall, the project demonstrates a complete regression workflow including exploratory data analysis, model training, coefficient interpretation, model evaluation, and comparison of actual and predicted Sales values.
