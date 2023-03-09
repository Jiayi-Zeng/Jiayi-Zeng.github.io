---
title: 1 Introduction of Deep Learning

date: 2022-10-25

tags: [ML]

categories: HUNG-YI LEE | MACHINE LEARNING

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303081247%20(2).png
---

# **Machine Learning ≈ Looking for function**

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053236150.png" alt="image-20221206053236150" style="zoom:50%;" class="center" />

# **Different Types of functions**

- **Regression**: The function outputs a scalar
- **Classification**: Given options (classes), the function outputs the correct one.
- **Structured Learning:** create something with structure (image, document)

![image-20221206053348699](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053348699.png)

# **How to find a function**

A case study

## The function we want to find …

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053424557.png" alt="image-20221206053424557" style="zoom: 33%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208221245405.png" alt="image-20221208221245405" style="zoom:180%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223257254.png" alt="image-20221208223257254" style="zoom:35%;"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223309541.png" alt="image-20221208223309541" style="zoom:50%;" />

![image-20221208223318275](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223318275.png)

![image-20221208223349650](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223349650.png)

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223401234.png" alt="image-20221208223401234" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223418427.png" alt="image-20221208223418427" style="zoom:50%;" />

# **ML Framework**

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053857892.png" alt="image-20221206053857892" style="zoom:50%;" class="center"/>

## Step1. Model

How to choose: Depend on *domain knowledge*

### Linear Models

Have *model Bias* (model limitation), 

$$
y = b + \sum_{j=1}^{n}w_jx_j
$$

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054003950.png" alt="image-20221206054003950" style="zoom:50%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054205148.png" alt="image-20221206054205148" style="zoom:50%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054210957.png" alt="image-20221206054210957" style="zoom:50%;" class="center"/>

### Sigmoid Function

Hard Sigmoid and Soft Sigmoid

![image-20221206054229272](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054229272.png)

![image-20221206054237612](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054237612.png)

$$
y=b+\sum_{i}c_isigmoid(b_i+w_ix_i)
$$

### New Model: More Features

![image-20221206054403705](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054403705.png)

**Hyperparameter:** 

* $j$ : no. of features
* $i$ : no. of sigmoid

![image-20221206054613829](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054613829.png)

![image-20221206054619581](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054619581.png)

### ReLu

![image-20221206054710081](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054710081.png)

### Deeper Model

![image-20221206054747992](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054747992.png)

## Step2. Loss

![image-20221206054758334](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054758334.png)

## Step 3. optimization

![image-20221206054825545](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054825545.png)

![image-20221206054848495](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054848495.png)

![image-20221206054855172](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054855172.png)

# **Deep Learning**

![image-20221206054927207](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054927207.png)

![image-20221208223439982](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223439982.png)



