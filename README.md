# Customer Churn Analysis & Prediction

An end-to-end machine learning project that analyzes customer behavior and predicts the likelihood of customer churn.

## Project Overview

This project uses customer data to identify patterns associated with churn and builds machine learning models to predict whether a customer is likely to leave a service.

The project covers:

- Data cleaning
- Exploratory Data Analysis (EDA)
- Data visualization
- Feature preprocessing
- Machine learning
- Model evaluation
- Interactive Streamlit dashboard

## Business Problem

Customer churn can significantly affect subscription-based businesses.

The goal of this project is to identify customers who are more likely to churn and understand the factors associated with customer attrition.

## Key Objectives

- Analyze customer churn patterns
- Identify high-risk customer segments
- Understand the relationship between customer characteristics and churn
- Build and compare machine learning models
- Provide an interactive churn prediction application


## Dataset

The project uses the Telco Customer Churn dataset containing customer demographics, subscribed services, contract information, billing details, and churn status.

### Dataset Statistics

- Original records: 7,043
- Original features: 21
- Records after cleaning: 7,032
- Target variable: `Churn`

## Exploratory Data Analysis

The analysis examined customer churn across different customer characteristics.

### Key Findings

- 73.42% of customers did not churn.
- 26.58% of customers churned.
- Churned customers had lower average tenure: approximately 18 months compared with 38 months for customers who stayed.
- Churned customers had higher average monthly charges: approximately 74 compared with 61 for customers who stayed.
- Customers with 0–12 months of tenure had the highest churn rate at approximately 47.68%.
- Churn decreased as customer tenure increased.

### Visualizations

The analysis includes visualizations for:

- Customer churn distribution
- Churn by contract type
- Churn by tenure
- Monthly charges vs churn
- Churn by internet service
- Churn by payment method


## Machine Learning

The project uses supervised machine learning to predict whether a customer is likely to churn.

### Machine Learning Workflow

1. Separate features and target variable
2. Split data into training and testing sets
3. Scale numerical features
4. Encode categorical features
5. Train classification models
6. Generate predictions
7. Evaluate model performance
8. Select the best-performing model

### Models Used

- Logistic Regression
- Random Forest Classifier

### Data Preprocessing

Numerical features were standardized using `StandardScaler`.

Categorical features were converted into numerical features using `OneHotEncoder`.

A `ColumnTransformer` was used to apply the appropriate preprocessing to each feature type.

### Train-Test Split

The cleaned dataset was divided into:

- 80% training data
- 20% testing data

Stratified splitting was used to maintain the churn class distribution across the training and testing datasets.


## Model Performance

The trained models were evaluated using multiple classification metrics.

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 80.38% | 64.85% | 57.22% | 60.80% | 83.59% |
| Random Forest | 78.96% | 63.45% | 49.20% | 55.42% | 81.40% |

### Selected Model

Logistic Regression was selected as the final model because it achieved better overall performance across the evaluated metrics.

The final model achieved:

- **80.38% Accuracy**
- **64.85% Precision**
- **57.22% Recall**
- **60.80% F1 Score**
- **83.59% ROC-AUC**


### Confusion Matrix

The Logistic Regression model produced:

```text
[[917, 116],
 [160, 214]]


- True Negatives: 917
- False Positives: 116
- False Negatives: 160
- True Positives: 214


```
## Streamlit Dashboard

A Streamlit-based interactive dashboard was developed to allow users to enter customer information and receive a churn prediction.

```
### Dashboard Features

- Customer information input form
- Churn probability prediction
- Churn risk classification
- Low / Medium / High risk interpretation
- Real-time prediction using the trained Logistic Regression model
- Saved preprocessing pipeline for consistent input transformation

```
## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Streamlit
- Joblib
- Jupyter Notebook
- Git & GitHub

```
## Project Structure

```text
customer-churn-analysis-prediction/
│
├── data/
│   └── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── notebooks/
│   └── 01_customer_churn_analysis.ipynb
│
├── models/
│   ├── logistic_churn_model.pkl
│   └── preprocessor.pkl
│
├── dashboard/
│   └── app.py
│
├── screenshots/
│
├── requirements.txt
├── .gitignore
└── README.md

```
## How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/zenudhay/customer-churn-analysis-prediction.git
cd customer-churn-analysis-prediction

```
### 2. Create a Virtual Environment

```bash
python -m venv venv

```
### 3. Activate the Virtual Environment

**Windows:**

```bash
venv\Scripts\activate

```
### 4. Install Dependencies

```bash
pip install -r requirements.txt

```
### 5. Run the Streamlit Dashboard

```bash
streamlit run dashboard/app.py

```
