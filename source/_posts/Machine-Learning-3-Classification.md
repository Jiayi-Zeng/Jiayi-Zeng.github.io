---
title: Classification

date: 2023-3-19 13:00

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303190258%20(3).png
---

**Classification as Regression?**

![image-20230317155425494](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230317155425494.png)

Class 1 and class 2 are more similar, class1 and class3 are not so similar.

# **1 Class as one-hot vector**

![image-20230317155813327](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230317155813327.png)

#  **2 Regression v.s. Classification**

![image-20230317160528628](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230317160528628.png)

# **3 Soft-max**

![image-20230317160836681](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230317160836681.png)

 

More commonly, it is always use sigmoid when binary classification (only 2 class), but sigmoid and soft-max are equivalent. 

# **4 Loss of Classification**

![image-20230319132037922](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319132037922.png)

**Minimizing cross-entropy** is equivalent to **maximizing likelihood**.

In Pytorch, when you call cross-entropy, it will include soft-max.

**Changing the loss function can change the difficulty of optimization.**

![image-20230317164853639](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230317164853639.png)

# **5 Classification**

## 5.1 Function with Unknow Parameters

![image-20230319133224159](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319133224159.png)

## 5.2 Loss of a function

![image-20230319134102718](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319134102718.png)

## 5.3 Training Examples

![image-20230319134835239](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319134835239.png)

![image-20230319135522107](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319135522107.png)

![image-20230319141422849](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319141422849.png)

### What do we want?

![image-20230319141750867](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319141750867.png)

![image-20230319141854769](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319141854769.png)

### Probability of Failure

![image-20230319142550890](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319142550890.png)

![image-20230319143515790](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319143515790.png)

![image-20230319143551236](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319143551236.png)

 

![image-20230319144451346](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319144451346.png)

### Tradeoff of Model Complexity -> Deep Learning

![image-20230319145023284](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319145023284.png)