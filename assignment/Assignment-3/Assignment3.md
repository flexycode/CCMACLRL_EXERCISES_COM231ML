# ✨ Intro to Machine Learning Assignment #3

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

# 🤖 Assignment 3: 

## Predicting Customer Purchase using Logistic Regression 
An online store wants to predict whether a visitor will **purchase a product $(y = 1)$** or **leave without buying $(y = 0)$**.  


We collect two features about each customer:

- $x_1$ = Time spent browsing the website (minutes)
- $x_2$ = Number of product pages viewed
- $y$ = Purchase outcome (1 = purchase, 0 = no purchase)

We need to use **logistic regression** to model the probability of purchase:

$$
\hat{y} = \sigma(w_1 x_1 + w_2 x_2 + b)
$$

where 

$$
\sigma(z) = \frac{1}{1+e^{-z}}
$$

---

## Dataset

| Customer | Time on site (x₁) | Pages viewed (x₂) | Purchase (y) |
|----------|-------------------:|------------------:|-------------:|
| A        | 1                  | 4                 | 0            |
| B        | 2                  | 3                 | 0            |
| C        | 3                  | 7                 | 1            |
| D        | 5                  | 2                 | 1            |
| E        | 6                  | 6                 | 1            |

Initial model parameters:
- $m_1 = 0.8$
- $m_2 = 0.4$  
- $b = -4.0$

---

## Tasks

### 1. Compute Probabilities (5 points)
For each customer A to E:

- Compute the linear score:  

$$
z = w_1 x_1 + w_2 x_2 + b
$$

- Compute the predicted probability:  

$$
\hat{y} = \sigma(z)
$$

| Customer | Time on site (x₁) | Pages viewed (x₂) | Purchase (y) | $\hat{y}$ 
|----------|-------------------:|------------------:|-------------:|-------------:|
| A        | 1                  | 4                 | 0            | 0.1680       |
| B        | 2                  | 3                 | 0            | 0.2315       |
| C        | 3                  | 7                 | 1            | 0.7685       |
| D        | 5                  | 2                 | 1            | 0.6900       |
| E        | 6                  | 6                 | 1            | 0.9608       |

### 2. Compute Average Loss (6 points)

Compute the Binary Cross-Entropy (BCE) loss for each sample:

$$
Loss = -\big[ y \ln(\hat{y}) + (1-y)\ln(1-\hat{y}) \big]
$$

- Fill in the table by reporting the **loss per customer**  
 
| Customer | Time on site (x₁) | Pages viewed (x₂) | Purchase (y) | $\hat{y}$ | $Loss$ |
|----------|-------------------:|------------------:|-------------:|-------------:|-------------:|
| A        | 1                  | 4                 | 0            | 0.1680       | 0.1840      |
| B        | 2                  | 3                 | 0            | 0.2315       | 0.2632      |
| C        | 3                  | 7                 | 1            | 0.7685       | 0.2632      |
| D        | 5                  | 2                 | 1            | 0.6900       | 0.3711      |
| E        | 6                  | 6                 | 1            | 0.9608       | 0.0399      |

  - Report the **average BCE loss** over all 5 customers  

$$
Loss_{avg} = \frac{1}{N} \sum_{i=1}^N Loss_i 
$$

$$
Loss_{avg} = \frac{0.1840 + 0.2632 + 0.2632 + 0.3711 + 0.0399}{5} = 0.2243
$$

$$
Loss_{avg} = 0.2243
$$



### 3. Update the slope and intercept using Gradient Descent (6 points)
   Perform **one step of gradient descent** with learning rate $\eta = 0.1$:  
   - Compute gradients of the loss w.r.t. $m_1, m_2, b$ 

$$
\frac{\partial L}{\partial m_1} = 0.1307 \quad
\frac{\partial L}{\partial m_2} = 0.0261, \quad
\frac{\partial L}{\partial b} = 0.1000?
$$

   - Calculate the new slopes $m_1, m_2$  and intercept $b$ :
     
$$
new m_1 = m_1 - \eta \frac{\partial L}{\partial m_1}, \quad 
new m_2 = m_2 - \eta \frac{\partial L}{\partial m_2}, \quad
new b = b - \eta \frac{\partial L}{\partial b}
$$

$$
new\ m_1 = 0.8 - 0.1×0.1307, \quad
new\ m_2 = 0.4 - 0.1×0.0261, \quad
new\ b = -4.0 - 0.1×0.1000
$$

$$
new m_1 = 0.7869, \quad
new m_2 = 0.3974, \quad
new b = -4.0100
$$

### 4. Compute new probabilities using the new slopes and intercept (5 points)

| Customer | Time on site (x₁) | Pages viewed (x₂) | Purchase (y) | new $\hat{y}$ 
|----------|-------------------:|------------------:|-------------:|-------------:|
| A        | 1                  | 4                 | 0            | 0.1633       |
| B        | 2                  | 3                 | 0            | 0.2236       |
| C        | 3                  | 7                 | 1            | 0.7562       |
| D        | 5                  | 2                 | 1            | 0.6725       |
| E        | 6                  | 6                 | 1            | 0.9566       |

Using: $new\ m_1 = 0.7869$, $new\ m_2 = 0.3974$, $new\ b = -4.0100$

<p>
 
**Customer A:** $z = 0.7869×1 + 0.3974×4 - 4.0100 = 0.7869 + 1.5896 - 4.0100 = -1.6335$
$\hat{y} = \sigma(-1.6335) = 0.1633$

$z = m_1 x_1 + m_2 x_2 + b = 0.7869×1 + 0.3974×4 + (-4.0100)$
$z = 0.7869 + 1.5896 - 4.0100 = -1.6335$ 

$\hat{y} = \sigma(-1.6335) = \frac{1}{1 + e^{1.6335}} = \frac{1}{1 + 5.1227} = \frac{1}{6.1227} = 0.1633$
</p>

<p>
 
**Customer B:** $z = 0.7869×2 + 0.3974×3 - 4.0100 = 1.5738 + 1.1922 - 4.0100 = -1.2440$
$\hat{y} = \sigma(-1.2440) = 0.2236$

$x_1 = 2, x_2 = 3$
$z = m_1 x_1 + m_2 x_2 + b = 0.7869×2 + 0.3974×3 + (-4.0100)$
$z = 1.5738 + 1.1922 - 4.0100 = -1.2440$ ✓

$\hat{y} = \sigma(-1.2440) = \frac{1}{1 + e^{1.2440}} = \frac{1}{1 + 3.4695} = \frac{1}{4.4695} = 0.2236$ ✓
</p>

<p>
 
**Customer C:** $z = 0.7869×3 + 0.3974×7 - 4.0100 = 2.3607 + 2.7818 - 4.0100 = 1.1325$
$\hat{y} = \sigma(1.1325) = 0.7562$

$x_1 = 3, x_2 = 7$
$z = m_1 x_1 + m_2 x_2 + b = 0.7869×3 + 0.3974×7 + (-4.0100)$
$z = 2.3607 + 2.7818 - 4.0100 = 1.1325$ ✓

$\hat{y} = \sigma(1.1325) = \frac{1}{1 + e^{-1.1325}} = \frac{1}{1 + 0.3220} = \frac{1}{1.3220} = 0.7562$ ✓
</p>

<p>
 
**Customer D:** $z = 0.7869×5 + 0.3974×2 - 4.0100 = 3.9345 + 0.7948 - 4.0100 = 0.7193$
$\hat{y} = \sigma(0.7193) = 0.6725$

$x_1 = 5, x_2 = 2$
$z = m_1 x_1 + m_2 x_2 + b = 0.7869×5 + 0.3974×2 + (-4.0100)$
$z = 3.9345 + 0.7948 - 4.0100 = 0.7193$ ✓

$\hat{y} = \sigma(0.7193) = \frac{1}{1 + e^{-0.7193}} = \frac{1}{1 + 0.4871} = \frac{1}{1.4871} = 0.6725$ ✓
</p>

<p>
 
**Customer E:** $z = 0.7869×6 + 0.3974×6 - 4.0100 = 4.7214 + 2.3844 - 4.0100 = 3.0958$
$\hat{y} = \sigma(3.0958) = 0.9566$


$x_1 = 6, x_2 = 6$
$z = m_1 x_1 + m_2 x_2 + b = 0.7869×6 + 0.3974×6 + (-4.0100)$
$z = 4.7214 + 2.3844 - 4.0100 = 3.0958$ ✓

$\hat{y} = \sigma(3.0958) = \frac{1}{1 + e^{-3.0958}} = \frac{1}{1 + 0.0453} = \frac{1}{1.0453} = 0.9566$ ✓
</p>


### 5. Compute new Average Loss (6 points)
- Fill in the table by computing the **new loss per customer**  
 

| Customer | Time on site (x₁) | Pages viewed (x₂) | Purchase (y) | $\hat{y}$ | new $Loss$ |
|----------|-------------------:|------------------:|-------------:|-------------:|-------------:|
| A        | 1                  | 4                 | 0            | 0.1633       | 0.1783       |
| B        | 2                  | 3                 | 0            | 0.2236       | 0.2531       |
| C        | 3                  | 7                 | 1            | 0.7562       | 0.2795       |
| D        | 5                  | 2                 | 1            | 0.6725       | 0.3969       |
| E        | 6                  | 6                 | 1            | 0.9566       | 0.0443       |


**Customer A:**
<p>
 
$Loss = -[y\ln(\hat{y}) + (1-y)\ln(1-\hat{y})]$
$Loss = -[0×\ln(0.1633) + (1-0)×\ln(1-0.1633)]$
$Loss = -[0 + 1×\ln(0.8367)] = -\ln(0.8367)$

$\ln(0.8367) = -0.1783$, so $Loss = -(-0.1783) = 0.1783$✓
</p>

<p>
 
**Customer B:**

$z = 0.7869×2 + 0.3974×3 - 4.0100 = 1.5738 + 1.1922 - 4.0100 = -1.2440$ 
$\hat{y} = \sigma(-1.2440) = 0.2236$ ✓
$Loss = -\ln(1-0.2236) = -\ln(0.7764) = 0.2531$ ✓
</p>

<p>
 
**Customer C:**

$z = 0.7869×3 + 0.3974×7 - 4.0100 = 2.3607 + 2.7818 - 4.0100 = 1.1325$ 
$\hat{y} = \sigma(1.1325) = 0.7562$ ✓
$Loss = -\ln(0.7562) = 0.2795$ ✓
</p>

<p>

**Customer D:**

$z = 0.7869×5 + 0.3974×2 - 4.0100 = 3.9345 + 0.7948 - 4.0100 = 0.7193$ 
$\hat{y} = \sigma(0.7193) = 0.6725$ ✓
$Loss = -\ln(0.6725) = 0.3969$ ✓

</p>

<p>
 
**Customer E:**

$z = 0.7869×6 + 0.3974×6 - 4.0100 = 4.7214 + 2.3844 - 4.0100 = 3.0958$ 
$\hat{y} = \sigma(3.0958) = 0.9566$ ✓
$Loss = -\ln(0.9566) = 0.0443$ ✓
</p>

- Report the **new average BCE loss** over all 5 customers. (Note: The new average loss must be lower than the previous average loss)

$$
$New\ Loss_{avg} = \frac{0.1783 + 0.2531 + 0.2795 + 0.3969 + 0.0443}{5} = \frac{1.1521}{5} = 0.2304$ ✓
$$

$$
New Loss_{avg} = 0.2304✓
$$


--- 🐍 CCMACLRL ASSIGNMENT 

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
    


