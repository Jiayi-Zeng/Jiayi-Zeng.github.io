---
title: 1 Introduction of Deep Learning

date: 2022-10-25

tags: [ML]

categories: HUNG-YI LEE | MACHINE LEARNING

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202302230549.png
---

# **Machine Learning ≈ Looking for function**

![image-20221206053236150](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053236150.png)

# **Different Types of functions**

- **Regression**: The function outputs a scalar
- **Classification**: Given options (classes), the function outputs the correct one.
- **Structured Learning:** create something with structure (image, document)

![image-20221206053348699](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053348699.png)

# **How to find a function**

A case study

## The function we want to find …

![image-20221206053424557](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053424557.png)

![image-20221208221245405](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208221245405.png)

![image-20221208223257254](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223257254.png)

![image-20221208223309541](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223309541.png)

![image-20221208223318275](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223318275.png)

![image-20221208223349650](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223349650.png)

![image-20221208223401234](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223401234.png)

![image-20221208223418427](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223418427.png)

# **ML Framework**

![image-20221206053857892](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053857892.png)

## Step1. Model

depend on domain knowledge

### Linear Models

have model bias (limitation), 

$$
y = b + \sum_{j=1}^{n}w_jx_j
$$


![image-20221206054003950](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054003950.png)

![image-20221206054205148](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054205148.png)

![image-20221206054210957](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054210957.png)

### Sigmoid Function

![image-20221206054229272](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054229272.png)

![image-20221206054237612](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054237612.png)

$$
y=b+\sum_{i}c_isigmoid(b_i+w_ix_i)
$$

### New Model: More Features

![image-20221206054403705](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054403705.png)

hyperparameter: 

* $i$ : no. of features
* $j$ : no. of sigmoid

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



