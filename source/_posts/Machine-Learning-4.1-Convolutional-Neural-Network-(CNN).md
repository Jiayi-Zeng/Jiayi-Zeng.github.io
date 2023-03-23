---
title: Convolutional Neural Network (CNN)

date: 2023-3-22 

tags: [ML]

categories: Machine Learning

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303190258%20(3).png
---



![image-20230319164917679](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319164917679.png)

![image-20230319165059549](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230319165059549.png)

## **1 Simplification 1**

### Observation 

![image-20230322200950874](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230322200950874.png)

### Simplification

![image-20230322201646461](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230322201646461.png)

### Typical Setting

![image-20230322202457980](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230322202457980.png)

## **2 Simplification 2**

### Observation

![image-20230322205832287](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230322205832287.png) 

### Simplification

![image-20230322210005981](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230322210005981.png)

**Two neurons with the same receptive field would not share parameters.**

![image-20230323093341152](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323093341152.png)

## **3 Benefit of Convolutional Layer**

![image-20230323093535628](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323093535628.png)

## **4 Another Story**

![image-20230323094048401](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323094048401.png)

### Multiple Convolutional Layers

The channel of next filters is the last filters number of convolution 

![image-20230323094941368](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323094941368.png)

Although the filter is 3$\times$3 on the second filter, but it consider 5$\times$5 area on the ordinary picture.

![image-20230323095338843](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323095338843.png)

## **5 Convolutional Layer**

![image-20230323095542834](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323095542834.png)

## **6 Pooling -Max Pooling**

![image-20230323095810366](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323095810366.png)

### Convolutional Layers + Pooling

![image-20230323095928760](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323095928760.png)

## **7 The Whole CNN**

![image-20230323100010610](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323100010610.png)

# **8 To Learn More**

Data Augmentation: Flip, scale, crop, rotation

Spatial Transformer Layer to improve this problem.

![image-20230323101213715](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230323101213715.png)