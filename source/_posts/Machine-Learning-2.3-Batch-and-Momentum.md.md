---
title: 2.3 Batch and Momentum

date: 2023-3-13 15:00

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303190258%20(1).png
---

# **1 Batch**

## 1.1 Review: Optimization with Batch

![image-20230313140211756](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313140211756.png)

## 1.2 Small Batch v.s. Large Batch

![image-20230313143835780](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313143835780.png)

### 1.2.1 Training Time

**Parallel Computing**

![image-20230313143623988](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313143623988.png)

![image-20230313143815916](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313143815916.png)

### 1.2.2 Performance

![image-20230313150746727](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313150746727.png)

* Small Batch size has better performance for **training data**.
* What's wrong with large batch size on training data?   **Optimization Fails.**
* Smaller batch size and momentum help escape critical points.

![image-20230313145045389](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313145045389.png)

* Small Batch size has better performance on **testing data**.
* What wrong with large batch size on testing data?    **Overfitting**

![image-20230313150215734](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313150215734.png)

**Flat Minima is better than Sharp Minima.**

![image-20230313151246458](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313151246458.png)

## 1.3 Comparison

![image-20230313151407854](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313151407854.png)

### 1.3.1 Reference

![image-20230313151502092](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313151502092.png)

# **2 Momentum**

## 2.1 (Vanilla) Gradient Descent

**Move in the opposite direction of gradient descent.**

![image-20230313152059377](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313152059377.png)

## 2.2 Gradient Descent + Momentum

**Movement: movement of last step minus gradient at present**

![image-20230313152522563](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313152522563.png)

$\mathbf{m^i}$ is the weighted sum of all the previous gradient: $\mathbf{g^0, g^1, ...,g^{i-1}}$

$$
\begin{align}
\mathbf{m^0} &= 0 \\
\mathbf{m^1} &= -\eta\mathbf{g^0} \\ 
\mathbf{m^2} &= -\lambda\eta\mathbf{g^0} - \eta\mathbf{g^1} \\
...
\end{align}
$$
