---
title: 3 Modeling Techniques

date: 2023-02-21

tags: [DSBA, ML]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230223%20(2).png
---

# **Modeling Methods**

| #    | Modeling Methods               | Response Variable: Numerical /Categorical | Supervised or Unsupervised | Strategy                              |
| ---- | ------------------------------ | ----------------------------------------- | -------------------------- | ------------------------------------- |
| 1    | Linear & Polynomial Regression | Numerical                                 | Supervised                 | Error Based<br/>Minimizing Error      |
| 2    | Logistic Regression            | Categorical (Binary)                      | Supervised                 | Maximizing Likelihood                 |
| 3    | Discriminant Analysis          | Categorical                               | Supervised                 |                                       |
| 4    | K Nearest Neighbor             | Categorical                               | Supervised                 | Similarity Based                      |
| 5    | Decision and Regression Trees  | Categorical + Numerical                   | Supervised                 | Information Based                     |
| 6    | Naïve Bayes                    | Categorical                               | Supervised                 | Probability Based                     |
| 7    | Neural Networks                | Numerical + Categorical                   | Supervised                 | Mimicking Human Brain                 |
| 8    | Clustering                     |                                           | Unsupervised               |                                       |
| 9    | Principal Component Analysis   |                                           | Unsupervised               |                                       |
| 10   | Support Vector Machines        | Categorical                               | Supervised                 | Error Based                           |
| 11   | ARIMA : Time Series            | Numerical                                 | Supervised                 | Auto Regression & Moving <br/>Average |

# **Estimation or Classification**

**Goals of Machine Learning Application: Estimation or Classification**

* **Estimation** – Regression modeling technique is used

  *Output is a number*

  * House price
  * Product sales for next quarter
  * GNP growth for the next quarter
  * Employment

* **Classification** – Naïve Bayes, Decision Trees etc. modeling techniques are used

  *Output is a categorical variable*

  * Sports team will win or lose
  * Email is junk or not
  * Which grade student will get
  * Tweet is positive or negative

# **Classification of Modeling Methods**

**Response Variable**

* Numerical or Categorical

**Supervised or unsupervised**

**Strategy**

* Error based learning
* Similarity Based Learning
* Information Based Learning
* Probability Based Learning
* Mimicking the Human Brain

# **Supervised vs. Unsupervised**

**Supervisor learning** is the most common learning type where **there is a target/output variable** (which is also called supervisor)

* Supervisor (target variable) teaches the algorithm how to build/learn the pattern model
* In PA, supervised learning ≈ predictive modeling

**Unsupervised learning has NO target variable**

* No supervisor to teach → algorithm has to learn by itself
* In PA, unsupervised learning ≈ descriptive modeling

![image-20230221112637145](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221112637145.png)

# **Classifying Based on Strategy to Build a Model**

## Error based learning

* Linear Multi Variable Regression
* Support Vector Machine

In error-based machine learning

* We perform a search for a set of parameters for a parameterized model
* That minimizes the total error across the predictions made by the model
* With respect to a set of training instances (training data)

![image-20230221113355334](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221113355334.png)

## Similarity Based Learning

* K Nearest Neighbor

Compute the distance matrices between objects

![image-20230221113427635](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221113427635.png)

## Information Based Learning

* Decision Trees
* Regression Trees
* Split of decision trees are based on the entropy of the tables

Learn by Asking Questions

* The Socratic approach to questioning is based on the practice of disciplined, thoughtful dialogue.
* Socrates, the early Greek philosopher/teacher, believed that disciplined practice of thoughtful questioning enabled the student to examine ideas logically and to determine the validity of those ideas.

![image-20230221113520227](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221113520227.png)

## Probability Based Learning

* Naïve Bayes

Provides a way to compute *reverse* probability. 

Given $P(B|A)$, we can compute $P(A|B)$

$$
P(A|B) = P(B|A)P(A)/P(B)
$$

Naïve Assumption: Assuming Variable Independence

## Mimicking the Human Brain: Neural Networks

* Extract linear combinations of the inputs
* Model the target as the non-linear functions of these features

![image-20230221113814241](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221113814241.png)

**Deep Learning:** Complex set of Neural Networks with many layers of processing

![image-20230221114146210](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230221114146210.png)

**Main Applications of Deep Learning Neural Networks**

* Image Recognition
  * Convolution Neural Networks
* Image Classification
  * Convolution Neural Networks
* Hand Writing Identification
* Speech Recognition
  * Long Short-Term Memory Networks