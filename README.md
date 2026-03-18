# Big Data Analytics – Final Project
## Titanic Survival Prediction with PySpark & MLlib

Project Structure
- Environment Setup
- Extract: Load raw data into Spark
- Transform: Clean, impute, engineer features
- Load: Save clean dataset
- Exploratory Data Analysis
- Predictive Model (MLlib)
- Visualizations

Spark version: 4.0.2
App name    : BigData_Titanic_FinalProject

### Stage 1 – EXTRACT
Load the raw Titanic CSV into a Spark DataFrame with an explicit schema.

Dataset source: Kaggle Titanic

Download train.csv and place it in the same folder as this notebook, or load directly from URL using the cell below.

### Stage 2 – TRANSFORM
Apply advanced data cleaning and feature engineering:

1. Quality check: Count nulls, duplicates, and run describe()
2. Missing values: Impute Age (median), fill Embarked (mode), drop Cabin
3. Duplicates: Detect and remove
4. Outliers: IQR-based detection on Fare and Age
5. Feature engineering: FamilySize, IsAlone, Title
6. Encoding: Index categorical columns for MLlib

### Stage 3 – LOAD
Persist the cleaned data in Parquet format — the industry standard for Spark because it is columnar, compressed, and schema-preserving.

### Stage 4 – EXPLORATORY DATA ANALYSIS (EDA)
Perform descriptive statistics, correlations, groupings, and frequency analysis using Spark DataFrames and Spark SQL.

### Stage 5 – PREDICTIVE MODEL (MLlib)
Algorithm Choice: Random Forest Classifier

Justification:
- Binary classification task (Survived = 0 or 1)
- Mix of numeric and categorical features
- Random Forest is robust to outliers, handles non-linearity, provides feature importances, and is resistant to overfitting through        ensemble averaging
- Naturally works with the MLlib Pipeline API
  
Pipeline stages:
1. StringIndexer → encode Sex, Embarked, AgeGroup, FareGroup
2. VectorAssembler → combine all features into a single vector
3. RandomForestClassifier → train the model

### Stage 6 – VISUALIZATIONS
Matplotlib, Seaborn, and Plotly charts covering:
- Survival distribution
- Survival by key features
- Correlation heatmap
- Feature importances
- Model performance (ROC curve)

