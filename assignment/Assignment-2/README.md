# Assignment 2: Linear Regression - Predicting Exam Scores

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

## 🎯 Problem Statement

This project implements a linear regression model to predict students' exam scores based on the number of hours they studied.

## 📊 Assignment Overview

We aim to fit a linear regression line of the form:
The implementation follows the Linear Regression demonstrated in the reference PDF.

---

### Task

We want to fit a **linear regression line** of the form:

$$
y = mx + b
$$

A new student studied **6 hours**. We want to predict the **Exam Score** using the regression equation.

---


Where:
- `y` is the Exam Score (dependent variable)
- `x` is the Hours Studied (independent variable)
- `m` is the slope of the regression line
- `b` is the y-intercept

## 📈 Data

| Student | Hours Studied (x) | Exam Score (y) |
|---------|-------------------|----------------|
| 1       | 1                 | 52             |
| 2       | 2                 | 57             |
| 3       | 3                 | 61             |
| 4       | 4                 | 65             |
| 5       | 5                 | 70             |

## 🧮 Calculations

### 1. Table Completion

| Student | Hours Studied (x) | Exam Score (y) | xy   | x²   |
|---------|-------------------|----------------|------|------|
| 1       | 1                 | 52             | 52   | 1    |
| 2       | 2                 | 57             | 114  | 4    |
| 3       | 3                 | 61             | 183  | 9    |
| 4       | 4                 | 65             | 260  | 16   |
| 5       | 5                 | 70             | 350  | 25   |
| **Total**| **Σx = 15**      | **Σy = 305**   | **Σxy = 959** | **Σx² = 55** |

---

### 2. Slope Calculation

$$
m = [n(Σxy) - (Σx)(Σy)] / [n(Σx²) - (Σx)²]
$$

$$
m = [5 × 959 - 15 × 305] / [5 × 55 - 15²]
$$

$$
m = [4795 - 4575] / [275 - 225]
$$

$$
m = 220 / 50
$$

$$
m = 4.40
$$

### 3. Intercept Calculation

```
b = (Σy - mΣx) / n
b = (305 - 4.40 × 15) / 5
b = (305 - 66) / 5
b = 239 / 5
b = 47.80
```

---


### 4. Regression Equation


$$
y = 4.40x + 47.80
$$

---



### 5. Predicted Values and Visualization

| Student | Hours Studied (x) | Exam Score (y) | Predicted Score (ŷ) |
|---------|-------------------|----------------|---------------------|
| 1       | 1                 | 52             | 52.20               |
| 2       | 2                 | 57             | 56.60               |
| 3       | 3                 | 61             | 61.00               |
| 4       | 4                 | 65             | 65.40               |
| 5       | 5                 | 70             | 69.80               |

[Regression Plot](assignment/Assignment-2/Assignment_2_Solution.ipynb)

---

### 6. Sum of Squared Errors (SSE)

| Student | y | ŷ | y - ŷ | (y - ŷ)² |
|---------|---|---|--------|-----------|
| 1       | 52 | 52.20 | -0.20 | 0.04      |
| 2       | 57 | 56.60 | 0.40  | 0.16      |
| 3       | 61 | 61.00 | 0.00  | 0.00      |
| 4       | 65 | 65.40 | -0.40 | 0.16      |
| 5       | 70 | 69.80 | 0.20  | 0.04      |

**SSE = 0.40**

---

### 7. Sum of Squared Total (SST)

Mean (ȳ) = 305 / 5 = 61.00

| Student | y | y - ȳ | (y - ȳ)² |
|---------|---|--------|-----------|
| 1       | 52 | -9.00  | 81.00     |
| 2       | 57 | -4.00  | 16.00     |
| 3       | 61 | 0.00   | 0.00      |
| 4       | 65 | 4.00   | 16.00     |
| 5       | 70 | 9.00   | 81.00     |

**SST = 194.00**

---

### 8. R-squared (R²) Calculation

$$
R² = 1 - (SSE / SST)
$$

$$
R² = 1 - (0.40 / 194.00)
$$

$$
R² = 1 - 0.0021
$$

$$
R² = 0.9979
$$

---


### 9. Prediction for 6 Hours

$$
y = 4.40 × 6 + 47.80
$$

$$
y = 26.40 + 47.80
$$

$$
y = 74.20
$$

---

## 📊 Final Results

| Metric | Value |
|--------|-------|
| Regression Equation | y = 4.40x + 47.80 |
| Slope (m) | 4.40 |
| Intercept (b) | 47.80 |
| SSE | 0.40 |
| SST | 194.00 |
| R² | 0.9979 |
| Prediction (6 hours) | 74.20 |

---

## 🔍 Interpretation

- **R² = 0.9979**: This indicates that 99.79% of the variance in exam scores is explained by hours studied, showing an excellent fit.
- **Slope = 4.40**: For each additional hour studied, the exam score increases by approximately 4.40 points.
- **The model predicts** that a student who studies for 6 hours would score approximately 74.20 on the exam.

### Git Commit Message: 📓 Assignment README.md 

---

#### [Back to Table of Content](https://www.youtube.com/watch?v=lqURPBtGJzg)

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
