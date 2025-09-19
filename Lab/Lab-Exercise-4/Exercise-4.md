# ✨ Intro to Machine Learning Exercise 4

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

## 🤖 Problem 


#### Instructions:

* You do not need to split your data. Use the training, validation and test sets provided below.
* Use Multinomial Naive Bayes to train a model that can classify if a sentence is a hate speech or non-hate speech
* A sentence with a label of zero (0) is classified as non-hate speech
* A sentence with a label of one (1) is classified as a hate speech

#### Apply text pre-processing techniques such as

* Converting to lowercase
* Stop word Removal
* Removal of digits, special characters
* Stemming or Lemmatization but not both
* Count Vectorizer or TF-IDF Vectorizer but not both

#### Evaluate your model by:

* Providing input by yourself
* Creating a Confusion Matrix
* Calculating the Accuracy, Precision, Recall and F1-Score
 
 
After collecting the data, use the notebook below to train your first machine learning model to predict your friends personality.
 
## 📓 Notebook link:
### 📜 [GitHub Link for Exercise](https://github.com/robitussin/CCMACLRL_EXERCISES/blob/main/Exercise4.ipynb)
 
## You can use this as reference:
### 📦 [Naive Bayes](https://github.com/robitussin/CCMACLRL/blob/main/6%20-%20Naive%20Bayes/implementation/Spam_Filter_using_Naive_Bayes.ipynb)
### 📦 [Naive Bayes Implementation](https://github.com/robitussin/CCMACLRL/blob/main/6%20-%20Naive%20Bayes/implementation/Naive_Bayes_In_Depth.ipynb)
### 📦 [Machine Learning repo ni idol Robitussin](https://github.com/robitussin/CCMACLRL/tree/main)

<!-- Always document your changes, pull-request, bugfix, updates, patch notes for this final project. Always use this "🧊 Flight Booking" for commiting message for "pushing code" or "Pull-request"   -->
# 📫 Changelogs & Documentation
This document summarizes all changes and bug fixes made to the Hate Speech Classification project using Multinomial Naive Bayes.

### 📦 Exercise no.4 - September 19, 2025
**Project Initialization**
- ✨ Created initial repository structure
- ✨ Set up project folder 
- ✨ Established ML development workflow & README.md
- 🔧 Initial google colab configuration and setup

### 🚀 Version History - September 20, 2025
**[Current Version] - Enhanced Text Cleaning & Bug Fixes**

- 🔧 Fixed duplicate removal issues:**
* ✨ Simplified from complex column-based deduplication to `df_train.drop_duplicates(inplace=True)`
* ✨ Resolved KeyError with 'cleaned_text' column not existing during early deduplication
- 🔧Fixed NaN handling problems:

* Replaced complex NaN filtering with simple df_train.dropna(inplace=True)

* Added proper handling for non-string inputs in preprocessing function

- ✨ Resolved text cleaning errors:

- ✨ Added input validation to handle NaN and non-string values

- ✨ Enhanced URL removal to catch both http and www patterns

- ✨ Added social media element removal (mentions, hashtags)

### ✨ Enhancements
**Improved text preprocessing:**

- ✨ Added comprehensive comments for all cleaning operations

- ✨ Enhanced date removal with multiple passes for different formats

- ✨ Added whitespace normalization and trimming

- ✨ Simplified data cleaning:

- ✨ Replaced complex multi-step cleaning with pandas built-in methods

- ✨ Maintained functionality while improving readability

- ✨ Enhanced multilingual support:

- ✨ Added proper handling for non-ASCII characters

- ✨ Improved support for Japanese, Tagalog, and Vietnamese text

- ✨ Better error handling:

- ✨ Added input validation in preprocessing functions

- ✨ Improved robustness against unexpected data types

### 📊 Performance Improvements
- ✨ Reduced code complexity from O(n) to O(1) for basic operations

- ✨ Memory efficiency through in-place operations

- ✨ Faster execution with optimized pandas methods

### 🧪 Testing Updates
- ✨ Added comprehensive test cases for multilingual inputs

- ✨ Verified proper classification (0 for non-hate, 1 for hate speech)

- ✨ Tested edge cases including empty strings and NaN values

### 📋 Technical Details
**Data Cleaning Pipeline**
- ✨ Input Validation: Check for NaN and non-string values

- ✨ Text Normalization: Convert to lowercase, remove line breaks

- ✨ Numerical Data Removal: Digits, currencies, dates

- ✨ Special Character Handling: Non-ASCII, punctuation

- ✨ Web Elements Removal: URLs, mentions, hashtags

- ✨ Whitespace Management: Extra space removal and trimming

- ✨ Model Performance
- ✨ Maintained original accuracy metrics while improving robustness

- ✨ Enhanced multilingual support without sacrificing English/Filipino performance

- ✨ Consistent results across validation and test sets

### 🔄 Backward Compatibility
**All changes maintain backward compatibility with:**

- ✨ Original dataset structure

- ✨ Model training pipeline

- ✨ Evaluation metrics

- ✨ Output formats

### 📈 Future Improvements
- ✨ Advanced multilingual support with language detection

- ✨ Context-aware preprocessing for different languages

- ✨ Enhanced model architecture for better cross-lingual performance

- ✨ Real-time preprocessing pipeline for production deployment


--- 🐍 CCMACLRL EXERCISES 

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
    

