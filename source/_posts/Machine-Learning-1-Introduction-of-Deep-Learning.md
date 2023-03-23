---

title: 1 Introduction of Deep Learning

date: 2022-10-25

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303081247%20(2).png
---

**Key Term:**

* Machine Learning ≈ Looking for function

* Different Types of Functions
  * Regression
  * Classification
  * Structured Learning

* How to find a function
  * Step1. Function with unknow parameters 
    ​	Model, weight, bias, feature
  * Step2. Define Loss from training Data
    ​	MAE, MSE, Cross-entropy, Error Surface
  * Step3. Optimization
    ​	Gradient Descent, Backpropagation Batch, Epoch
* Model
  ​	Activate Funtion
  * Linear Model
  * Sigmoid Function
  * ReLu

# **1 Machine Learning ≈ Looking for function**

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053236150.png" alt="image-20221206053236150" style="zoom:50%;" class="center" />

# **2 Different Types of Functions**

- **Regression**: The function outputs a scalar
- **Classification**: Given options (classes), the function outputs the correct one.
- **Structured Learning:** create something with structure (image, document)

![image-20221206053348699](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053348699.png)

# **3 How to find a function**

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206053424557.png" alt="image-20221206053424557" style="zoom: 33%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208221245405.png" alt="image-20221208221245405" style="zoom:180%;" class="center"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223257254.png" alt="image-20221208223257254" style="zoom:35%;"/>

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223309541.png" alt="image-20221208223309541" style="zoom:50%;" />

![image-20221208223318275](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223318275.png)

![image-20221208223349650](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223349650.png)

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223401234.png" alt="image-20221208223401234" style="zoom:50%;" />

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221208223418427.png" alt="image-20221208223418427" style="zoom:50%;" />

# **4 ML Framework**

![image-20230323115143560](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323115143560.png)

## Step1. Model

How to choose: Depend on *domain knowledge*

### Linear Models

Have *model Bias* (model limitation), 

$$
y = b + \sum_{j=1}^{n}w_jx_j
$$

### Sigmoid Function

#### Hard Sigmoid

![image-20230323105514175](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323105514175.png)

#### Soft Sigmoid

$$
y=b+\sum_{i}c_isigmoid(b_i+w_ix_i)
$$

![image-20230323105558324](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323105558324.png)

#### Change parameter

![image-20221206054237612](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054237612.png)

### New Model: More Features

![image-20221206054403705](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054403705.png)

**Hyperparameter:** 
* $j$ : no. of features
* $i$ : no. of sigmoid

![image-20221206054613829](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054613829.png)

![image-20221206054619581](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054619581.png)

Can be seen as **Matrix Operation** (Why call GPU when Training)

### ReLu

![image-20221206054710081](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054710081.png)

### Deeper Model

![image-20221206054747992](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054747992.png)

### Fully Connect Feedforward Network

This is a function. Input vector, output vector.

Given network structure, define **a function set**.

**![image-20230323112155743](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323112155743.png)**

* The costum model is to do feacture engineering, which is to do feature transform to find good features. 
  The deep learning does not need to find good features. It means it just use pixels. But it needs to design the structure of neural network.
  
* Can the structure be automatically determined?
  E.g. Evolutionary Artificial Neural Networks

## Step2. Loss

* Loss is a function of parameters $L(\theta)$
* Loss means how good a set of values is.

![image-20230323133054604](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323133054604.png)

$$
Loss: L=\frac{1}{N}\sum_ne_n
$$

### Regularization

If some noises corrupt input $x_i$ when testing, a smoother function has less influence.

![image-20230323132806193](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323132806193.png)

It has the better performance when we don't consider **bias** on the $\lambda\sum(w_i)^2$ 

![image-20230323133558954](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323133558954.png)

* Training erroe: larger $\lambda$, considering the training error less.
* We prefer smooth function, but don't be too smooth.

## Step 3. Optimization

### Optimization of New Model

![image-20221206054825545](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054825545.png)

### Backpropogation

![image-20230323120718394](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323120718394.png)

![image-20230323120743453](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323120743453.png)

### Backpropagation - Backward Pass

![image-20230323121417013](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323121417013.png)

$$
\frac{\partial{C}}{\partial{z}}=\sigma'(z)[w_3\frac{\partial{C}}{\partial{z'}}+w_4\frac{\partial{C}}{\partial{z''}}]
$$

![image-20230323121836443](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323121836443.png)

Compute $\frac{\partial{C}}{\partial{z}}$ recursively, until we reach the output layer.

> **Chain Rule**
>
> ![image-20230323120042742](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323120042742.png)



### Batch & Epoch

![image-20221206054855172](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20221206054855172.png)

* Suppose we have 1k data, the batch size is 100,
  * so the number of update in 1 epoch will be 10.

### Backpropagation

An efficient way to compute $\frac{\partial{L}}{\partial{w}}$in neural network.

# **5 Deep Learning**

* Many layers means Deep -> Deep Learning

### Why don't we go deeper?

**Overfitting**: Better on training data, worse on unseen data.

![image-20230323104612097](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323104612097.png)

***figure**: Loss for mutiple hidden layers*

## 5.1 History of Deep Learning

![image-20230323110254713](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323110254713.png)
