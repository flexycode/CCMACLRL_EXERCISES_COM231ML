# Exercise 3: Titanic Survival Prediction with Logistic Regression

## 📖 Project Overview

This project implements a machine learning solution to predict passenger survival on the Titanic using logistic regression. The solution follows a complete data science pipeline from exploratory data analysis to model deployment.

**Competition Link**: [Kaggle Titanic - Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic)

## 🎯 Problem Statement

The sinking of the Titanic is one of the most infamous shipwrecks in history. This challenge asks us to build a predictive model that answers the question: **"what sorts of people were more likely to survive?"** using passenger data (ie name, age, gender, socio-economic class, etc).

## 📊 Dataset Description

The data has been split into two groups:
- **Training set** (`train.csv`): Used to build our machine learning models
- **Test set** (`test.csv`): Used to see how well our model performs on unseen data

### Features Description

| Variable | Definition | Key |
|----------|------------|-----|
| survival | Survival | 0 = No, 1 = Yes |
| pclass | Ticket class | 1 = 1st, 2 = 2nd, 3 = 3rd |
| sex | Sex | |
| Age | Age in years | |
| sibsp | # of siblings / spouses aboard | |
| parch | # of parents / children aboard | |
| ticket | Ticket number | |
| fare | Passenger fare | |
| cabin | Cabin number | |
| embarked | Port of Embarkation | C = Cherbourg, Q = Queenstown, S = Southampton |

## 🛠️ Solution Approach

### 1. Exploratory Data Analysis (EDA)
- Analyzed survival rates by different features
- Identified patterns and correlations
- Handled missing values appropriately

### 2. Feature Engineering
Created new features to improve model performance:
- **Title**: Extracted from names (Mr, Mrs, Miss, Master, Rare)
- **FamilySize**: Combined SibSp and Parch
- **IsAlone**: Flag for passengers traveling alone
- **AgeGroup**: Binned age into meaningful categories
- **FareGroup**: Binned fare into quartiles
- **Deck**: Extracted from cabin numbers

### 3. Data Preprocessing
- Handled missing values with appropriate imputation strategies
- Encoded categorical variables using Label Encoding
- Scaled numerical features for logistic regression

### 4. Model Training
- Used **Logistic Regression** with L2 regularization
- Implemented pipeline with StandardScaler
- Performed train-validation split for model evaluation
- Used cross-validation for robust performance estimation

### 5. Model Evaluation
- Achieved competitive accuracy on validation set
- Analyzed confusion matrix and classification report
- Interpreted feature importance through coefficients

## 📈 Key Insights

### Factors Increasing Survival Probability:
- **Female passengers** (strong positive coefficient)
- **Higher passenger class** (1st class > 2nd class > 3rd class)
- **Lower fare groups** (inverse relationship observed)
- **Specific titles** (Mrs, Miss had higher survival rates)

### Factors Decreasing Survival Probability:
- **Male passengers**
- **Lower passenger classes**
- **Certain embarkation ports**

## 🚀 How to Run

### Google Colab
1. Open the notebook in Google Colab using the provided badge
2. Run all cells sequentially
3. The submission file will be generated automatically

### Local Environment
```bash
# Install required packages
pip install pandas numpy matplotlib seaborn scikit-learn

# Run the notebook
jupyter notebook Exercise3.ipynb