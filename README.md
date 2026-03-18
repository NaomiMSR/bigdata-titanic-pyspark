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
