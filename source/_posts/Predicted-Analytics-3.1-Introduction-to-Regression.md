---
title: 4 Introduction to Regression

date: 2023-02-22

tags: [DS, ML, Data Mining]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230223%20(3).png
---

# **Definition: Linear Regression**

**2 variable regression** - how a response variable $y$ changes the predictor (explanatory) variable $x$ changes.
$$
y = \beta_1x + c
$$

**Multiple regression** - how a response variable $y$ changes as the predictor (explanatory) variables $x1$, $x2$, ... $xn$ change
$$
y = \beta_1x_1+\beta_2x_2+\beta_3x_3+...+\beta_nx_n+c
$$

**Single Variable Polynomial Regression: First degree to Fifth Degree**

The concept can be extended to polynomial regression

$$
\begin{align}
y &= c + a_1x \\
y &= c + a_1x + a_2x^2 \\
y &= c + a_1x + a_2x^2 + a_3x^3 \\
y &= c + a_1x + a_2x^2 + a_3x^3 + a_4x^4 \\
y &= c + a_1x + a_2x^2 + a_3x^3 + a_4x^4 + a_5x^5 \\
y &= c + a_1x + a_2x^2 + a_3x^3 + a_4x^4 + a_5x^5 +a_nx^n\\
\end{align}
$$

# **Regression Strategy: Ordinary Least Squares (OLS)**

The least-squares regression line of y and x is the 
line that makes the sum of the squares of the vertical 
distances of the data points from the line as small as 
possible.

![image-20230222092629577](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230222092629577.png)

# Regression: Supervised Learning Method

Single split model assessment methodology

* The model is tested on hold-out sample
* Only the hold-out sample accuracy is reported

![image-20230306002607033](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306002607033.png)

# **Nearest Neighbor Regression**

A method for predicting a numerical variable $y$, given a value of $x$:

* Identify the group of points for which the values of $x$ are close to the given value
* The prediction is the average of the $y$ values for the group

**Graph of Averages**

* For each value of $x$, the predicted value of $y$ is the average of the $y$ values of the nearest neighbors.
* Graph these predictions for all the values of $x$, That's the **graph of average**
* If the association between the two variables is linear, then points on the graph of averages tend to fall on near a straight line. That's the **regression line.**

# Solution for Regression Line

* Residual = Observed value – Computed Value

Suppose regression equation is
$$
y = mx+b
$$

* $y$ is the explanatory variable, $x$ is the predictor variable
* $m$ is the slope of the line, $b$ is the intercept

$$
\begin{align}
Residual &= y_i-(mx_i+b)\\
Residual^2 &= (y_i-(mx_i+b))^2\\
ResidualSumOfSquares &= RSS = \sum_{i=1}^{N}(y_i-(mx_i+b))^2
\end{align}
$$

* To find the minimum point of this function, we will take the partial derivative of RSS with respect to ‘m’ and ‘b’ and set that to zero.

![image-20230306005620610](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306005620610.png)

![image-20230306005637510](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306005637510.png)
$$
\begin{align}
m &= \frac{\sum(y_ix_i)-\frac{\sum(y_i)\sum(x_i)}{N}}{\sum(x_i^2)-\frac{\sum(x_i)^2}{N}}\\
b &= (\frac{\sum(y_i)}{N}-m\frac{\sum(x_i)}{N})
\end{align}
$$

## Method 1

![image-20230306010108743](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306010108743.png)

![image-20230306010118579](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306010118579.png)

![image-20230306010129262](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230306010129262.png)

# Example

## #1 Galton

[galton.ipynb](https://colab.research.google.com/drive/1EsqPlpKab6Ko7YXQzjLxe0kVI88L3341)  [galton.csv](https://drive.google.com/file/d/1R3n46DKTH_jXpkUaE_D0jOQ1mzblXTEk/view?usp=sharing)

## #2 Using skLearn and staysmodel

[P1_Dictionary.ipynb](https://colab.research.google.com/drive/1rfAxSYwvt0VAW7Z6oDrpfGb5j9TP-yZs)

## #3 FULL CODE_Regression_Model

[FULL CODE_Regression_Model_Advertising.ipynb](https://colab.research.google.com/drive/1fLiSvyb-y4cQR8MFPMc7ZytbgOTjRBr7)
