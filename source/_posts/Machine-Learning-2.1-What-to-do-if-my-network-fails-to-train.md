---
title: 2.1 What To Do If My Network Fails To Train

date: 2023-3-8

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303190258%20(4).png
---

![image-20230307235457606](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307235457606.png)

# **1 Model Bias** 

![image-20230323131344456](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323131344456.png)

### Solution: Redesign model to make it more flexible

![image-20230323131440148](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323131440148.png)

# **2 Optimization Issue**

![image-20230323131110970](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323131110970.png)

### **Model Bias v.s. Optimization Issue**

* Start from shallower network (or other models), which are easier to optimize.
* If deeper networks do not obtain smaller loss on **training data**, then there is **optimization issue.**

![image-20230323131851971](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323131851971.png)

# **3 Overfitting**

A more complex model yields lower error on training data.

But large loss on testing data.

![image-20230308001204296](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308001204296.png)

### Solution

1. **More training data**

![image-20230323130811173](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323130811173.png)

2. **Data Augmentation**

![image-20230323130837409](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323130837409.png)



![image-20230308001820638](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308001820638.png)

* Fully-Connected is more flexible, 

  CNN is relatively less flexible, and the constrain is relatively large.

### Too much constrain back to model bias

![image-20230308001941564](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308001941564.png)

# **4 Bias-Complexity Trade-off**

![image-20230308002114624](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308002114624.png)

### Solution: Cross Validation

![image-20230323131622971](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323131622971.png)

### **N-fold Cross Validation**

![image-20230308003859200](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308003859200.png)

# **5 Mismatch**

Your training and testing data have different distributions.

![image-20230308004235701](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230308004235701.png)

### Solution: To understand how data is generated.
