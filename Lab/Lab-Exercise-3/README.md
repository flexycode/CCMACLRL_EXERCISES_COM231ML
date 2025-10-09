# ✨ Intro to Machine Learning Exercise 3

### Name: [Jay Arre Talosig](https://www.youtube.com/watch?v=-er2ruCgzjg&list=RDfFqxDrmQLnQ&index=4)  
### Subject & Section: [CCMACLRL - COM231ML](https://www.youtube.com/watch?v=fFqxDrmQLnQ&list=RDfFqxDrmQLnQ&start_radio=1)
### Schedule: [TUE 11:00AM - 01:40 PM VR09CCIT - FRI 11:00AM - 03:00 PM 408 MB](https://www.youtube.com/watch?v=dL7Vn7hJDAk&list=RDdL7Vn7hJDAk&start_radio=1)
### Professor: [Elizer Ponio Jr](https://github.com/robitussin/)     

<!-- 🤖 Machine Learning 🤖 -->
<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3N3lpMjVqNnE3dWh4Mzk0cnF4N2RhcWJudmxvc3RqMW0waHFiN3R5MCZlcD12MV9zdGlja2Vyc19zZWFyY2gmY3Q9cw/jY1r8EHyk4Ye9KUOUb/giphy.gif" width="250">
<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3b3pjaDIydDdpZXBnZWRxMWVuOWMyeDV1dHU0c3N5N243eDcyaWVkZCZlcD12MV9zdGlja2Vyc19zZWFyY2gmY3Q9cw/rYchHXYdIDp3Qpt3IK/giphy.gif" width="300">
<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3N3lpMjVqNnE3dWh4Mzk0cnF4N2RhcWJudmxvc3RqMW0waHFiN3R5MCZlcD12MV9zdGlja2Vyc19zZWFyY2gmY3Q9cw/jY1r8EHyk4Ye9KUOUb/giphy.gif" width="250">
</div>


# 🤖 Exercise 3: Titanic Survival Prediction with Logistic Regression

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
```

<!-- Introduction Pannel button link, it will redirect to the top -->

#### [Back to Table of Content](https://www.youtube.com/watch?v=2gJJzspizFk&list=RDfFqxDrmQLnQ&index=13)

<!-- End point line insert Thanks for visiting enjoy your day, feel free to modify this  -->
---

<p align="center">
<img src="https://readme-typing-svg.demolab.com/?lines=Thanks+For+Visiting+Enjoy+Your+Day+~!;" alt="mystreak"/>
</p>

<!-- Siero Miero -->
<div align="center">
<img src="https://media.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3OGJ0aW80YnkwcjdmNzdzZ2tuMDdpaTZydzV5dTQ3M2VtdXlrd2k0ayZlcD12MV9zdGlja2Vyc19zZWFyY2gmY3Q9cw/iF7FoIWjpHD7E2ndx4/giphy.gif" width="300">
</div>

<!-- End point line insert Comeback again next time, feel free to modify this  -->
<p align="center">
<img src="https://readme-typing-svg.demolab.com/?lines=Come+Back+Again+next+time" alt="mystreak"/>
</p>

</p>
    

