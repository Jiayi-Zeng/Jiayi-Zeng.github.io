---
title: 2 Introduction to Predictive Modeling

date: 2023-02-20

tags: [DSBA, ML]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/20230223%20(1).png
---

Data analysis involves a number of modeling techniques that can be classified as three main types:

- Predictive
- Clustering
- Association

# **Predictive Modeling**

*Predictive modeling*, sometimes called ***supervised learning***, focuses on understanding or making predictions about a given variable based on one or more other variables. **The ultimate goal of predictive analysis is accuracy**. For example, you may want to predict which potential customers are more likely to apply for a credit card based on a knowledge of their demographic and financial information. In this scenario, there are two types of variables:

- **The** **dependent variable** **or** **target**: The variable you are trying to predict or understand (i.e., the likelihood of applying for a credit card)
- **The** **independent variables** **or predictors**: The variables you are using as a basis for predicting or understanding the target variable (i.e., demographic and financial information)

Below are several additional applications of predictive modeling:

- Determining which students in a class will pass or fail
- Predicting which parts of a city will experience increasing crime (predictive policing)
- Forecasting the number of unfilled hotel rooms three months from now
- Projecting which patients are likely to have a heart attack
- Estimating how much each customer will purchase when shopping online
- Classifying shipping containers according to the likelihood that they carry drugs or weapons
- Identifying IP addresses that are sending unusual amounts of information

# **Cluster Analysis**

Cluster analysis, or segmentation, is a type of unsupervised learning problem that is very different from predictive modeling. Cluster analysis is appropriate when you can associate each case in a dataset with other cases that share similar distinct characteristics. You end up with several groups, in which the members of each group are very similar to each other but very different compared to members of other groups.

Cluster analysis is often used in marketing campaigns so that customers receive ads tailored for the group to which they belong rather than generic ads. These groups are identified via cluster analysis. In such a scenario, there is no dependent variable; only independent variables are used to segment the cases.

Cases in which the variables have similar values are grouped into *clusters* in an attempt to find homogenous subsets. Determining the number of clusters to create is part of the challenge of such techniques. Since clustering is exploratory in nature, the resulting clusters are not necessarily right or wrong. Instead, cluster solutions should be judged by their ability to address the specific business problem you are trying to solve. Applications of cluster analysis include:

- Market research
- Plant and animal ecology
- Medical imaging (e.g., PET Scans)
- Service/product usage pattern identification
- Social network analysis
- Crime analysis
- Anomaly detection

# **Association Modeling**

Companies like Amazon and Netflix have made *association modeling* commonplace. As consumers, most of us have encountered recommendation engines where a movie is recommended based upon our prior viewing habits or books are recommended based on our prior purchases (or even just our prior browsing behavior). **Association models use transactional data to predict future transactions.** The idea is that you may be able to suggest additional items that a person may want or need based on their previous buying behavior. This results in statements such as, “People who bought product A and product B might also like product C” appearing on their computer screens.

Association modeling is often described primarily as a kind of market basket analysis, but while it is strongly associated with retail data, it can also be applied in other areas. For example, in predictive maintenance, a pair of part failures might frequently be associated with the failure of a third part even though that third part doesn’t show evidence of trouble at the time the first two fail.

**Transactions in association models often occur at the same time.** For instance, many items might be listed on a grocery store receipt, but, there is no indication of which purchases occurred before others. Hot dogs and hot dog buns may be frequently purchased together, but there is no “rule” that indicates which purchase occurred first. In a predictive model, you might say that hot dogs “predict” buns or that buns predict hot dogs. A further refinement involves ***sequence analysis***, which does take into consideration the order in which events, such as purchases, occur. This can be useful in predictive maintenance or in web mining, where it might be beneficial to know the sequence in which website visitors click on links and buttons on a page or move to other pages in the site.

Applications of association modeling include:

- Market basket analysis
- Retail data analysis
- Web usage 
- Insurance claim analysis
- Service usage
- Medical procedures

# **Overview of Predictive Models**

This course covers only some of the most popular predictive models. Specifically, we’ll take a look at the following:

- Statistical models
- Decision Tree models
- Machine Learning models

## Statistical Models

***Statistical models* produce equations and *statistical tests* guide predictor selection. These models make certain assumptions whereas *rule induction* and *machine learning* models do not.** Here are several characteristics of statistical predictive models:

- Predictions are expressed as equations.
- Equations allow users to see the effect of a one-unit change on any field and how this change impacts the outcome variable.
- Predictive models are based on statistical theory, which involves developing hypotheses and assessing statistical significance. This allows you to easily identify the important variables.
- Predictive models involve assumptions about the data, which may limit the situations in which some models can be used.

Below is a list of some statistical models.

- Logistic Regression
- Discriminant Analysis
- Linear Regression
- Generalized Linear Models
- Cox Regression
- Time Series

## Decision Tree Models

A *decision tree* or *rule induction model* is an important type of predictive model. It derives a set of rules in relation to a dependent variable. The model’s output shows the reasoning for each rule and can therefore be used to understand the decision-making process that drives a particular outcome. Models that produce decision trees belong to this class of models. Generally, decision tree predictive models:

- Create segments that are mutually exclusive and exhaustive (identify homogeneous subgroups)
- Create rules for making predictions about individual cases
- Can easily handle a large number of predictors
- Can account for interaction and non-linear relationships
- Have few assumptions
- Can create overly complex models that over-fit data (does not generalize)

Below is a list of several rule induction models:

- CHAID
- CART
- C5.0
- QUEST
- Decision List
- MARS

## Machine Learning Models

*Machine learning models* are optimized for learning complex patterns. Unlike traditional statistical techniques, no assumptions are made about the data. Machine learning models do not produce a set of rules like rule induction models, nor do they produce easy-to-understand equations like statistical models. Thus, machine learning models are often said to be “black box” models. They produce a set of equations, but because there is a hidden layer (possibly several hidden layers), the interpretation of the coefficient weights is not straightforward as it is with traditional statistical models or rule induction models. Machine learning predictive models:

- Are optimized for learning complex patterns
- Can account for interaction and non-linear relationships
- Have few assumptions 
- Are essentially “black box” models—their interpretation is not straight-forward
- Are used for predictive accuracy but not for understanding the mechanics behind a prediction

Below is a list of several machine learning models:

- Neural Networks
- Support Vector Machines
- Random Forest
- Naïve Bayesian Algorithms
- Gradient Boosting Algorithms
- K-Nearest Neighbors

# **Model Validation**

The process of statistical hypothesis testing, which involves a result’s statistical significance in the context of certain data distribution assumptions (such as having normally distributed errors), helps us determine when we have found a valid and reliable result. However, most data-mining methods do not depend on specific data distribution assumptions for drawing inferences from the sample to the population. So how is validation achieved? Model validation in data mining is usually done by partitioning the data into training and testing datasets. Models are developed from the training data and then the models’ predictions are tested on the testing data. Validity is established by demonstrating that the model applies to data different from what was used to derive the model. Statisticians often recommend such validation for statistical models, but it is crucial for more general (less distribution-bound) data-mining techniques.

# **How to Choose a Model**

Choosing a model is difficult. Obviously, if you have a variable in the data file that you want to predict, then any of the predictive models (depending on the target variable’s level of measurement) will perform the task albeit with varying degrees of success. If you want to find groups of individuals that behave similarly on a number of fields in the data, then any of the clustering methods are appropriate. The use of association rules, while not directly giving you the ability to make predictions, are extremely useful as a tool for understanding the various patterns within the data.

However, determining which particular prediction technique will work best depends specifically on how the variables you want to predict are related to the predictors. There are suggested guidelines as to when one technique may work better than another, but these are only suggestions and not rules.

From the previous discussion, it follows that more than one prediction model can be used to predict an outcome. The business context provides the first deciding factor in selecting a model. For example, if your goal is to extract a set of rules from the model, a rul*e induction model* is the only choice. Alternatively, if the model itself is of no interest but must nevertheless be as accurate as possible, then any of the models could be a candidate for the task. When one class of model is preferred but there are many models within that class, how do you choose a specific model?

Each model has different characteristics when it comes to they way in which:

- Missing values are handled
- Continuous predictors are handled
- Categorical predictors are handled
- Outliers are handled
- The number of predictors impacts prediction
- The model scores data

There are many subtle differences between the models. In the end, however, it is always the business users who balance the pros and cons, and decide which model or combination of models should be used. There is a wide range of possibilities and it is only the business user who can decide what to do.

Data analytics and reporting tools such as KNIME provide for simplicity in building models. Machine learning models, rule induction models (decision trees), and statistical models can be built with great ease and speed, and their results compared. You must remember that data mining is an iterative process: models will be built, broken down, and often even combined before the user is satisfied with the results.

One final yet important point to keep in mind when building models is that software will only find rules or patterns in data if they actually exist. You cannot extract a model with high predictive accuracy if there are no associations between the predictors and dependent variables.

# **Reference** 

**Course text:** UCI. (2020). [Introduction to Predictive Modeling. ](https://docs.google.com/document/d/1lQI25BjQD4mNhVDyDWjfn7x1cFlfKfX6NnXl0zUUKIw/edit?usp=sharing)

