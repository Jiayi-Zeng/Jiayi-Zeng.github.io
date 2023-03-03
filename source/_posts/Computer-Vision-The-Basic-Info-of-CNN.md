---
title: Basic Knowledge of CNN

date: 2022-03-27

tags: [CV]

categories: Computer Vision

post_asset_folder: ture

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/-%20LeNet%20(1998)%20(1).png
---

简单介绍卷积神经网络中常见的全连接层，卷积层、池化层以及误差反向传播过程和训练优化器的原理。

<!--more-->

# **1 卷积神经网络 CNN**

* 卷积神经网络，即包含卷积层的神经网络。
* 第一个卷积神经网路：LeCun的LeNet（1998）网络结构

![Net_LeNet](https://github.com/Jiayi-Zeng/Jiayi-Zeng.github.io/blob/pic/img/Net_LeNet_covoer.png?raw=true)

## 1.1 CNN的发展

![](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327213127062.png)

## 1.2 CNN的应用

图像检测、图像检索、图像检测、图像分割、无人驾驶、GPU、图像迁移

![image-20220327213228684](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327213228684.png)

![image-20220327213244394](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327213244394.png)

![image-20220327213324662](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327213324662.png)

# **2 神经元**

![image-20220403112023201](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220403112023201.png)

$$
y=f(x_1·w_1+x_2·w_2+x_3·w_3-1)
$$

其中，$x$为激励，$w$为神经元连接权值，$-1$为偏置，$f(x)$为激活函数。

# **3 全连接层**

![image-20220403113627551](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220403113627551.png)

# **4 BP神经网络**

## 4.1 BP神经网络简介

**BP（Back Propagation）算法包括信号的前向传播和误差的反向传播两个过程**，即计算误差输出时按从输入到输出的方向进行，而调整权值和阈值则从输出到输入的方向进行。

## 4.2 BP神经网络实例

### 1.输入层

1. 彩色RGB图像 --> 灰度化--> 灰度图像 --> 二值化--> 二值图像

![image-20220327214232774](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327214232774.png)

2. 窗口滑动：计算白色像素占整个框像素的比例

![image-20220327214413416](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327214413416.png)

3. 按行展开，拼接成**行向量（神经网络输入层）**

![image-20220327214508874](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327214508874.png)

### 2. 输出层

**one-hot编码**

![image-20220327214704028](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327214704028.png)

### 3. 神经网络

![image-20220327214728420](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327214728420.png)

# **5 卷积层**

**目的：**进行图像特征提取

**特性：**拥有局部感知机制，权值共享（减少参数）

> **权值共享**
>
> ![image-20220327215001204](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327215001204.png)

## 5.1 卷积过程

![SouthEast](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/SouthEast.gif)

![image-20220327215117151](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327215117151.png)

通过观察可以发现：

* **`卷积核channel`与`输入层的channel`相同**
* **输出的`特征矩阵channel`与`卷积核个数`相同**

## 5.2 激活函数

目的：**引入非线性因素，使其具备解决非线性问题的能力。**

1. **`Sigmoid`激活函数**

* 饱和时梯度非常小，故网络层数较深时易出现梯度消失。
* 计算多类损失最后使用`softmax`激活函数，经过`softmax`处理后所有输出节点概率和为1。

$$
o_1=\frac{e^{y_1}}{e^{y_1}+e^{y_2}}\\
o_2=\frac{e^{y_2}}{e^{y_1}+e^{y_2}}
$$

2. **ReLU激活函数**

* 缺点在于当反向传播的过程中有一个非常大的梯度经过时，反向传播更新后可能导致权重分布中心小于0，导致该处的倒数始终为0，反向传播无法更新权重，即进入失活状态。
* 失活后无法“复活”。建议一开始不使用较大学习率，否则大多数神经元容易失活。

![image-20220327215434274](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220327215434274.png)

## 5.3 越界情况

利用**padding**补零，经卷积后的矩阵尺寸大小计算公式为：

$$
N=(W-F+2P)/S+1
$$

其中，输入图片大小为$W×W$，`Filter`大小为$F×F$，步长为$S$，`padding`的像素数为$P$.

# **6 池化层**

目的：对特征图进行稀疏处理，减少数据运算量

* 没有训练参数
* 只改变特征矩阵`W`和`h`，不改变`channel`
* 一般`pool size`和`stride`相同

1. **MaxPooling 下采样层**

![image-20220403114548879](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220403114548879.png)

2. **AveragePooling 下采样层**

![image-20220403114623086](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220403114623086.png)

# **7 反向传播**

## 7.1 误差计算

**Cross Entropy Loss 交叉熵损失**

1. 针对**多分类**问题（最后一层为**softmax**输出，所有输出概率和为1）

$$
H=-\sum_io^*log(o_i)
$$

2. 针对**二分类**问题（最后一层为**sigmoid**输出，输出节点之间相互不相干）

$$
H=-\frac{1}{N}\sum_{i=1}^N[o_i^*log(o_i)+(1-o_i^*)log(1-[o_i)]
$$

其中，$o_i^*$为真实标签值，$o_i$为预测值，默认$log$=$ln$

## 7.2 误差的反向传播

![image-20220328221513797](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328221513797.png)

![image-20220328221543152](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328221543152.png)

![image-20220328221622680](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328221622680.png)

## 7.3 权重的更新

![image-20220328221732785](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328221732785.png)

![image-20220328221848547](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328221848547.png)

# **8 优化器 optimizer**

![image-20220328222050506](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222050506.png)

## 8.1 SGD

![image-20220328222130228](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222130228.png)

## 8.2 SGD+Momentum优化器

![image-20220328222335145](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222335145.png)

## 8.3 Adagrad优化器（自适应学习率）

![image-20220328222425119](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222425119.png)

## 8.4 RMSProp优化器

![image-20220328222528324](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222528324.png)

## 8.5 Adam优化器（自适应学习率）

![image-20220328222551419](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20220328222551419.png)