# Clustering Analysis of Employee Mental Health Risks

## Content

- [Background & Problem Statement](#background--problem-statement)
- [Objective](#objective)
- [Method](#method)
- [Execution Steps](#execution-steps)
- [Main Findings](#main-findings)
- [Conclusion](#conclusion)

## Objective
This project aims to develop and evaluate three machine learning algorithms to cluster employee mental health risk profiles. The ultimate goal is to identify the model that best supports risk recognition and provides actionable insights for employers to take early preventive measures.


## Dataset
Source: ​[Mental Health dataset from Kaggle](https://www.kaggle.com/datasets/mahdimashayekhi/mental-health)

The dataset is a synthetic simulation that reflects real-world patterns observed in workplace mental health data. The dataset includes 10,000 individuals and 14 variables, encompassing demographic attributes such as age, gender, and employment type, as well as information about the work environment, mental health scores, and related actions.

**Data Summary:**

| **Variables**             | **Data Summary**                        |
|---------------------------|-----------------------------------------|
| Age                       | Average: 41.6 years                     |
| Gender                    | Male (46%); Female (45%); Other (9%)   |
| Employment Status         | Employed (59%); Student (20%); Other (21%) |
| Work Environment          | On-site (50%); Remote (30%); Other (19%) |
| Mental Health History     | True (30%); False (70%)                 |
| Seeks Treatment           | True (40%); False (60%)                 |
| Stress Level              | Average: 5.6                            |
| Sleep Hours               | Average: 6.5                            |
| Physical Activity Days    | Average: 3.5                            |
| Depression Score          | Average: 15.0                           |
| Anxiety Score             | Average: 20.6                           |
| Social Support Score      | Average: 50.1                           |
| Productivity Score        | Average: 77.3                           |
| Mental Health Risk        | High (24%); Medium (59%); Low (17%)     |


## Tools 
Python, Jupyter Notebook, Visual Studio Code

## Clustering Algorithms
- K-Means
- Agglomerative clustering (Ward Linkage)
- Mean Shift

## Data Cleaning
Comprehensive checks were performed to ensure data integrity:
- Missing Values: None detected across any variables
- Outliers or Abnormal Values: No anomalies found
- Duplicate Records: None identified in the dataset
As all checks returned clean, no further data cleaning steps were required.

## Feature Engineering

**Correlation between Variables:**

- A strong negative correlation was observed between depression_score and productivity_score, with a correlation coefficient of -0.93, indicating that higher levels of depression are closely associated with reduced productivity.
- No significant signs of collinearity were detected among the remaining variables, suggesting that each contributes uniquely to the clustering process.
- Pair plot analysis shows no clear linear relationships among the remaining​ variables. However, it reveals that the distribution of each feature varies distinctly across the three levels of mental_health_risk: Low, Medium, and High (Figure 1).

**Feature Selection:** 
- Given the requirements of the clustering algorithms, only numerical variables were retained as features. Additionally, productivity_score was excluded due to its high collinearity with depression_score, which could distort clustering outcomes.
- A total of five features were selected for training the clustering models:
  - sleep_hours
  - physical_activity_days
  - depression_score
  - anxiety_score
  - social_support_score
​​- Note: mental_health_risk is a categorical variable and was not included as a feature in the clustering analysis. However, it was converted to an ordinal data type for future evaluations—such as assessing cluster alignment with risk levels.​​

**Feature Scaling:** 
- ​Standardization (Z-score Normalization) was applied to scale features to avoid the algorithm overvalue the features with larger scales. The scaled features have values range from -1 to 1 (mean of 0 and standard deviation of 1).

**Skewness check:** 
- ​No significant skewness was detected in any of the numerical variables, indicating a relatively balanced distribution across the dataset.

## Model Training Summary
