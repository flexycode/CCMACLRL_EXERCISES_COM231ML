# Assignment 1: k-Nearest Neighbors (k-NN) - Student Pass/Fail Prediction

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

## 📋 Assignment Overview
This assignment implements the k-Nearest Neighbors (k-NN) algorithm to predict whether a student will pass or fail based on their study hours and sleep patterns. The implementation follows the k-NN methodology demonstrated in the reference PDF.

## 🎯 Problem Statement
Predict if a student will **Pass (1)** or **Fail (0)** based on:
- **X₁** = Hours Studied
- **X₂** = Sleep Hours

**New Student Data:** Studied **4 hours** and slept **6 hours**
**Algorithm:** k-NN with **k = 3**

## 📊 Training Data
| Student | Hours Studied (X₁) | Sleep Hours (X₂) | Pass/Fail (Y) |
|---------|-------------------|------------------|---------------|
| 1       | 1.0               | 5.0              | 0 (Fail)      |
| 2       | 2.0               | 5.5              | 0 (Fail)      |
| 3       | 3.0               | 6.0              | 0 (Fail)      |
| 4       | 4.5               | 5.0              | 0 (Fail)      |
| 5       | 5.0               | 6.5              | 1 (Pass)      |
| 6       | 5.5               | 7.0              | 1 (Pass)      |
| 7       | 6.0               | 6.0              | 1 (Pass)      |
| 8       | 7.0               | 7.0              | 1 (Pass)      |
| 9       | 8.0               | 6.0              | 1 (Pass)      |
| 10      | 9.0               | 7.5              | 1 (Pass)      |

---
## 🐍 1: Plot all data points using a scatter plot (10 points)

- Use a circle 🔵 for students who failed.
- Use a square 🟥 for students who passed.
- Use a star ⭐ for the unknown data point.

[Answer Result is here in this Link](https://github.com/flexycode/CCMACLRL_EXERCISES_COM231ML/blob/main/assignment/Assignment-1/Assignment_1_Solution.ipynb)


---

## 🧮 2: Compute Distances (10 points)
Using the Euclidean distance formula:
\[d = \sqrt{(X_1 - 4)^2 + (X_2 - 6)^2}\]

### Complete Distance Table
| Student | Hours Studied (X₁) | Sleep Hours (X₂) | Pass/Fail (Y) | Euclidean Distance |
|---------|-------------------|------------------|---------------|-------------------|
| 1       | 1.0               | 5.0              | 0             | 3.162             |
| 2       | 2.0               | 5.5              | 0             | 2.062             |
| 3       | 3.0               | 6.0              | 0             | 1.000             |
| 4       | 4.5               | 5.0              | 0             | 1.118             |
| 5       | 5.0               | 6.5              | 1             | 1.118             |
| 6       | 5.5               | 7.0              | 1             | 1.803             |
| 7       | 6.0               | 6.0              | 1             | 2.000             |
| 8       | 7.0               | 7.0              | 1             | 3.162             |
| 9       | 8.0               | 6.0              | 1             | 4.000             |
| 10      | 9.0               | 7.5              | 1             | 5.315             |

---

## 🔍 2. Find the 3 Nearest Neighbors (3 points)

### 3 Nearest Neighbors (k=3)
The 3 smallest distances are:

| Student | Hours Studied (X₁) | Sleep Hours (X₂) | Pass/Fail (Y) | Euclidean Distance |
|---------|-------------------|------------------|---------------|-------------------|
| **3**   | **3.0**           | **6.0**          | **0**         | **1.000**         |
| **4**   | **4.5**           | **5.0**          | **0**         | **1.118**         |
| **5**   | **5.0**           | **6.5**          | **1**         | **1.118**         |

---

## 🗳️ 3: Majority Vote (k=3) (2 points)

Count how many are **Pass (1)** and how many are **Fail (0)**.
Predict the outcome for the new student.

- **Pass (1) votes:** 1
- **Fail (0) votes:** 2

**Prediction:** A new student who studied 4 hours and slept 6 hours will **FAIL (0)** the exam.

---

## 🔬 Additional Analysis: k=5 Scenario

### 5 Nearest Neighbors
| Student | Hours Studied (X₁) | Sleep Hours (X₂) | Pass/Fail (Y) | Euclidean Distance |
|---------|-------------------|------------------|---------------|-------------------|
| **3**   | **3.0**           | **6.0**          | **0**         | **1.000**         |
| **4**   | **4.5**           | **5.0**          | **0**         | **1.118**         |
| **5**   | **5.0**           | **6.5**          | **1**         | **1.118**         |
| **6**   | **5.5**           | **7.0**          | **1**         | **1.803**         |
| **7**   | **6.0**           | **6.0**          | **1**         | **2.000**         |

---

### Majority Vote (k=5)
- **Pass (1) votes:** 3
- **Fail (0) votes:** 2

**Prediction with k=5:** A new student who studied 4 hours and slept 6 hours will **PASS (1)** the exam.

---

## 📈 Visualization
The scatter plot shows:
- 🔵 **Blue circles**: Students who failed (0)
- 🟥 **Red squares**: Students who passed (1)
- ⭐ **Purple star**: New student (4 hours studied, 6 hours slept)

[This section is here in this link](https://github.com/flexycode/CCMACLRL_EXERCISES_COM231ML/blob/main/assignment/Assignment-1/Assignment_1_Solution.ipynb)

The visualization clearly shows the new student positioned in a transitional region between the pass and fail clusters.

---

## 💡 4. Discussion Questions

### 1. What was your final prediction?
**Final Prediction with k=3:** The new student will **FAIL (0)** the exam.

### 2. How would the prediction change if we used k=5 instead of k=3?
The prediction **changes from FAIL (0) to PASS (1)** when using k=5. This demonstrates the sensitivity of k-NN to the choice of the k parameter. With k=3, the majority of nearest neighbors are failing students, while with k=5, the additional neighbors include more passing students, shifting the majority vote.

## 🎯 Key Insights
1. **k parameter sensitivity**: The choice of k significantly impacts the prediction outcome
2. **Decision boundary**: The new student lies close to the decision boundary between pass and fail classes
3. **Feature importance**: Both study hours and sleep patterns contribute to academic performance
4. **Algorithm behavior**: k-NN is sensitive to local data distribution near the query point

---

## 📚 Algorithm Reference
This implementation follows the k-NN methodology from the reference PDF:
- Euclidean distance calculation
- Nearest neighbor selection
- Majority voting classification
- Parameter k sensitivity analysis

The results demonstrate practical application of k-NN prediction tasks.

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
