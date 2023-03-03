---
title: 4 Introduction to Regression

date: 2023-02-22

tags: [DSBA, ML, Data Mining]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230223%20(3).png
---

# **Linear Regression – Ordinary Least Square (OLS)**

2 variable regression - how a response variable $y$ changes the predictor (explanatory) variable $x$ changes.

$$
y = \beta_1x + c
$$

Multiple regression - how a response variable $y$ changes as the predictor (explanatory) variables $x1$, $x2$, ... $xn$ change

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

**Regression Strategy: Ordinary Least Squares (OLS)**

![image-20230222092629577](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230222092629577.png)

# **Nearest Neighbor Regression**

A method for predicting a numerical variable $y$, given a value of $x$:

* Identify the group of points for which the values of $x$ are close to the given value
* The prediction is the average of the $y$ values for the group
* 