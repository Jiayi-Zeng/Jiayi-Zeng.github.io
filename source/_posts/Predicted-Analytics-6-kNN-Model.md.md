---
title: 8 kNN Model

date: 2023-02-27

tags: [DS, Data Mining]

categories: "Predicted Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303060126%20(5).png
---

# **1 Similarity Based Learning**

![image-20230307135237509](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135237509.png)

**Compute the distance matrices between objects**

![image-20230307135320379](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135320379.png)

# **2 k Nearest Neighbor (kNN) Model**

## 2.1 Pros and Cons of kNN

| Pros                                                         | Cons                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| Simple and Effective                                         | Does not produce a model, limiting the ability to understand how the features are related to the class |
| Makes no assumption about the underlying data distribution<br/>Non-parametric | Requires selection of an appropriate value of ‘k’            |

## 2.2 Example

![image-20230307135514058](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135514058.png)

![image-20230307135528439](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135528439.png)

![image-20230307135551335](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135551335.png)

![image-20230307135600672](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135600672.png)

![image-20230307135654082](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135654082.png)

![image-20230307135706642](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135706642.png)

# **3 kNN Model Assessment**

![image-20230307135731080](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135731080.png)

![image-20230307135744961](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135744961.png)

# **4 Data Normalization: Standardization & Scaling**

Suppose we have 2 data items

* Height: varies from 4 – 7 feet
* Net Worth: $10,000 - $100B

If we use both the variables in a model

* Net Worth will dominate because it contains large values

Solution

* Standardize
* Scale

## 4.1 Data Standardization and Scaling

![image-20230307135919181](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307135919181.png)

# **5 kNN in Python**

[03_kNN_Optimum_k_Iris_Sci_L_ConMat.ipynb](https://colab.research.google.com/drive/1rkJLDzQ-40DtU-MPmGMYTANrwNn_wNeo)
