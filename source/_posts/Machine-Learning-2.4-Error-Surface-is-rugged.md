---
title: 2.4 Error Surface Is Rugged...

date: 2023-3-14

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303081247%20(3).png
---

Tips for training: **Adapting Learning Rate**

# **1 Training stuck ≠ Small Gradient**

![image-20230313154301877](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313154301877.png)

![image-20230313155019805](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313155019805.png)

# **2 Different Parameters Needs Different Learning Rate**

![image-20230313155516527](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313155516527.png)

$t$: iteration,  $i$: one of the parameter 

## 2.1 Adagrad: Root Mean Square (RMS)   

![image-20230313160205168](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313160205168.png)

## 2.2 RMSProp

Learning rate adapts dynamically on the same direction.![image-20230313160502530](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313160502530.png)

<img src="https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313160825876.png" alt="image-20230313160825876" style="zoom: 40%;" class="center"  />

![image-20230313161102967](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313161102967.png)

## 2.3 Adam: RMSProp + Momentum

![image-20230313161134024](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313161134024.png)

## 2.4 Learning Rate Scheduling

![image-20230313161654334](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313161654334.png)

![image-20230313162445753](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313162445753.png)

**Warm up is used in Residual, Transformer, Bert**

![image-20230313162203813](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313162203813.png)

## 2.5 Summary of Optimization

![image-20230313162728082](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230313162728082.png)