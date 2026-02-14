# MSCS 634 – Project Deliverable 2  
## Regression Modeling and Performance Evaluation

---

## Project Overview

This project focuses on building and evaluating regression models using the Health Stroke dataset. The objective was to apply feature engineering techniques and compare multiple regression models to predict a continuous target variable.

For this deliverable, **BMI (Body Mass Index)** was selected as the outcome variable.

---

## Dataset Summary

The dataset includes demographic and medical features such as:

- Age  
- Hypertension  
- Heart Disease  
- Average Glucose Level  
- Stroke  
- BMI  

The dataset was cleaned and preprocessed (from Deliverable 1), including handling missing values, encoding categorical variables, and standardizing numerical features.

---

## Feature Engineering

The following preprocessing steps were applied:

- Removal of irrelevant columns (e.g., ID)
- Handling missing values
- Encoding categorical variables
- Feature scaling using standardization
- Creation of interaction features where appropriate

These steps ensured model stability and improved predictive performance.

---

## Regression Models Implemented

Three regression models were developed and compared:

1. Linear Regression  
2. Ridge Regression  
3. Lasso Regression  

Regularization techniques were included to evaluate whether coefficient penalization improves generalization.

---

## Cross-Validation Results (5-Fold)

| Model               | Mean CV R² | Mean CV MSE | Mean CV RMSE |
|---------------------|------------|------------|--------------|
| Lasso Regression    | 0.2852     | 31.1399    | 5.5801       |
| Ridge Regression    | 0.2833     | 31.2207    | 5.5873       |
| Linear Regression   | 0.2830     | 31.2343    | 5.5885       |

---

## Final Model Performance (Test Set)

The best-performing model, **Lasso Regression**, achieved:

- **Test R²:** 0.3101  
- **Test MSE:** 31.4852  
- **Test RMSE:** 5.6112  

The test R² of 0.31 indicates that approximately 31% of the variance in BMI is explained by the predictors. The RMSE of 5.61 suggests predictions deviate from actual BMI values by about 5.6 units on average.

The similarity between cross-validation and test results indicates strong model generalization and minimal overfitting.

---

## Key Insights

- BMI demonstrates moderate predictability using available health features.
- Regularization (Lasso) slightly improved performance by reducing the impact of less significant features.
- A large portion of BMI variability is likely influenced by unobserved factors such as diet, genetics, and lifestyle.
- The dataset may be more naturally suited for classification tasks than high-precision regression.

---

## Challenges

- Weak to moderate feature correlations.
- Limited explanatory variables.
- Preventing data leakage during preprocessing and cross-validation.

---

## Moderate R² Value

One of the primary challenges in this project was the relatively moderate R² value (approximately 0.21–0.31 depending on model and validation split). An R² in this range indicates that the model explains only about 21–31% of the variance in BMI, meaning a substantial portion of variability remains unexplained.

### Why Might the R² Be Moderate?

Several factors may explain this outcome:

- **Limited Feature Set:** The dataset contains basic demographic and medical indicators but does not include important lifestyle variables such as diet, physical activity, genetics, or socioeconomic factors, all of which significantly influence BMI.
- **Weak Linear Relationships:** Correlation analysis showed weak relationships between BMI and many predictors, limiting the effectiveness of linear regression models.
- **Natural Biological Variability:** BMI is influenced by complex physiological and environmental factors, making it difficult to model precisely using a small set of features.
- **Model Assumptions:** Linear, Ridge, and Lasso regression assume linear relationships. If the true relationships are nonlinear, performance will naturally be limited.
- **Measurement Noise:** Real-world health datasets often contain noise, missing data, or measurement inconsistencies that reduce predictive strength.

### Implications for Data Analysis

The moderate R² does not indicate model failure. Instead, it highlights important realities in applied data science:

- Not all datasets are strongly predictable.
- Real-world data often contain hidden variables not captured in structured datasets.
- Model performance must be interpreted in context rather than judged by a fixed numerical threshold.

---


## Conclusion

This deliverable successfully applied feature engineering, implemented multiple regression models, and evaluated performance using cross-validation and test metrics.

The results demonstrate proper regression modeling methodology and provide meaningful insight into the predictive structure and limitations of the dataset.

This outcome reinforces the importance of understanding domain limitations, feature relevance, and model assumptions when conducting regression analysis.

