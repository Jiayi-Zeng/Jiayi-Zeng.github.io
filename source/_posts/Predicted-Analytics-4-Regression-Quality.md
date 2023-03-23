---
title: 6 Regression Quality

date: 2023-02-25

tags: [DS, Data Mining]

categories: "Predicted Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303060126%20(3).png
---

Metrics to measure the Quality of Regression 

* Correlation between the response variable and predictor variables 
* Root Mean Square Error (RMSE) 
* R-square + Adjusted R-Square 
* p-values of the predictor variables 
* Residuals are normally distributed. 

# **1 Measure of Regression**

![image-20230307111851997](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307111851997.png)

**Total Deviation = Explained Deviation + Unexplained Deviation**

**SST = SSR + SSE**

* SST = Total Sum of Squares = Total Deviation
* SSR = Regression Sum of Squares = Explained Deviation
* SSE = Error Sum of Squares = Unexplained Deviation

![image-20230307112029424](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307112029424.png)

## 1.1 Coefficient of Determination r^2

**Definition**

$$
r^2 = \frac{explainedVariation}{totalVariation}=\frac{SSR}{SST}
$$


**How to compute $r^2$**

$$
squareCorrelationValue = r^2 = 1-\frac{SSE}{SST}
$$

The closer $r^2$ is to $1$, the better the fir. For a perfect fit, $SSE = 0$, $r^2 =1$

# **2 Standard Error**

Standard error is the standard deviation of **the deviation of actual response variable with the predicted variable (residuals)** using the regression line.

Degree of freedom

* Two variables are estimated: Slope, Intercept
* Lose 2 degree of freedom: $df=n-2$

$$
s_e=\sqrt{\frac{\sum(y_i-\hat{y_i})^2}{n-2}}=\sqrt{\frac{\sum(residuals)^2}{n-2}}=\sqrt{\frac{SSE}{n-2}}
$$

# **3 Verify that the residuals are normally distributed**

**If the residuals are not normally distributed, regression is not Valid**

## 3.1 Histogram

Plot the histogram of the data, see a normal distribution

**Problem with this technique**

* Histograms shape change with different bin sizes

## 3.2 QQ Plot - Quantile-Quantile plot

Data is plotted against a theoretical normal distribution. If you see a straight line, data is normally distributed

**Testing Procedure**

* First Sort the data
* Plot against appropriate quantiles from the standard normal distribution
  * Divide the normal distribution curve into (n+1=10) parts, each part represents 10% of the area
  * Compute the corresponding z-values

QQ plot is

* X axis: z-values taken from the standard normal distribution curve
* Y-axis: Sorted Data values

![image-20230307133050546](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307133050546.png)