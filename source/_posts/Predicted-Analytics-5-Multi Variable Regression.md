---
title: 7 Multi Variable Regression

date: 2023-02-26

tags: [DS, Data Mining]

categories: "Predicted Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303060126%20(4).png
---

# **1 Multiple Variables Regression**

**Definition**

How a response variable $y$ changes as the predictor (explanatory) variables $x1$, $x2$, ... $xn$ change

In a $n$ variable regression,

* There is 1 response variable $y$
* And $n$ predictor variables $x1$, $x2$, $x3$, ... $xn$, Goal is to find the values of $\beta1$, $\beta2$, $\beta3$, ... $\beta{n}$

$$
y = \beta_1x_1+\beta_2x_2+\beta_3x_3+...+\beta_nx_n+c
$$

**Regression Strategy**

Same strategy used in the 2-variable regression: The least-squares regression line of y and x is the line that makes 

* the sum of the squares of the vertical distances of the data points from the line as small as possible

# **2 Correlation between Multiple Variables**

## 2.1 Correlation Matrix

**Definition: Correlation**

A correlation matrix shows the linear correlation between each pair of variables under consideration in a multiple regression model

**Predictor Variables Selection Criteria in Multi Regression**

* Predictor variables should have a high linear correlation with the response variable
* But do not include variables that are highly correlated among themselves

**Multi-collinearity**

Multi-collinearity exists between 2 explanatory (predictor) variables if they have a high linear correlation

# **3 Normality of Residuals**

![image-20230307134215162](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307134215162.png)

![image-20230307134223716](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307134223716.png)

# **4 Test Individual Regression Coefficients for Significance**

## 4.1 Coefficient: p-value

Since both p-values are sufficiently small

* We reject both the NULL hypothesis
* There is a linear relationship between both the predictor variables and the response variable

If the p-value for the slope coefficient is large

* We should consider removing it from the model

# **5 Example**

[P1_x1x2x3x4y.ipynb](https://colab.research.google.com/drive/1cWNHzXwddnd2cudiIZ9twv3Gxc7jSkNu)
