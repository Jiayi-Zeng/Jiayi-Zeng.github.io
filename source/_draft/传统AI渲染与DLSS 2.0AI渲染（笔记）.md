# 传统AI渲染与DLSS 2.0AI渲染的在理论、工作原理、效果上的区别及案例介绍

[TOC]

## 【笔记1】[硬件科普] 免费提升画质和帧数？详解DLSS2.0的工作原理与作用

### DLSS 2.0 20系显卡

显卡的**常规升级**通常升级性能或是DirectX支持，20系列显卡则包括

* **RT Core** 实时光线演算功能 RTX

* **Tensor core** 张量计算核心 作用：增加显卡AL的深度学习计算功能

  <img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102154857722.png" alt="image-20220102154857722" style="zoom:33%;" />

  <img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102154944304.png" alt="image-20220102154944304" style="zoom:33%;" />

### 传统CUDA核心无法完成的功能：DLSS深度学习超采样

### 分辨率和性能消耗的平衡：抗锯齿

* **SSAA** 超级取样抗锯齿
* **MSAA** 多重取样抗锯齿
* **MFAA** 多帧采样抗锯齿
* **FXAA** 快速近似抗锯齿
* **SMAA** 子像素增强抗锯齿
* **TXAA** 时间近似抗锯齿
* **DLAA** 深度学习抗锯齿

### AI 

* 在人类看不出规律的情况下根据曾经看过的大数据强行总结出一个可以推断将来可能性准确率比较高的公式。
* 依托于大数据，模拟神经网络思考的优化算法。

### DLSS 1.0 AI脑部画面

* 两个阶段

  * 训练阶段：找出低分辨率到高分辨率可行性较高的规律，并总结出一个算法
  * 使用阶段：把这个算法融入显卡驱动和游戏引擎，游戏时渲染图片

  <img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102160133931.png" alt="image-20220102160133931" style="zoom:50%;" />

* 缺陷：在没有规律中找到可行性较高的规律，并非事物客观本身存在的规律，可能导致颜色出错。游戏中出现画面模糊、运动场景中产生大量的伪影和重影。
* 模糊补偿方案：Geforec experience游戏滤镜加上锐化效果（降低帧数，用帧数换清晰度）

### DLSS 2.0 

* 借助AL完成多帧合成
*  **TAA**（抗锯齿） 
  * 渲染时不再对全屏幕进行采样，分区采样
  * 类比**HDR**：通过对画面不同区域进行曝光，合并多张不同曝光的画面
  * 静态画面很好使用，动态画面出现**鬼影现象**。通过手调算法减少鬼影现象
* DLSS2.0 基于TAA这种多帧合并进行改进 人工手调 → AI实时演算
  * 借助原有信息进行多时段度空间的复用，提高效率
  * 采样点、时间变多 静态画面更清晰 动态画面做到相似（人眼对于动态画面不敏感的特性，质量降低会被直接忽略）
* **总结** 如果要渲染4K的游戏画面
  * **原生4K** 显卡从头到尾把4K图像完整渲染一遍，纯粹傻算
  * **DLSS 1.0** 渲染1080P的画面，用AI脑补到4K分辨率上，纯靠猜
  * **DLSS 2.0** 渲染一堆采样点和采样时间不同的1080P的画面，通过多帧合成到4K分辨率上，不会产生FXAA后处理的模糊，不会产生TAA动态鬼影

### DLSS 1.0 vs DLSS 2.0

* DLSS 1.0 每个游戏厂商还要针对自己的游戏去进行针对性AI训练，需要对自己的游戏训练自己的算法才能完成DLSS超采样和抗锯齿的功能。
* DLSS 2.0 引入大量通用模型和算法，使其可以应用于所有的游戏，不需要单独去训练AI，大幅度降低接入DLSS功能门槛
* 已经接入DLSS1.0的游戏必须接入新的SDK开发优化才能接入2.0

### 总结

DLSS 2.0 

分辨率不变，近一倍帧数提升，提高显卡利用率，降低性能负担，提高帧数，缓解因为光线追踪导致得帧数大幅度的下降。不降低游戏画面的同时，由于多帧合成，在部分场景还能超过原本渲染的原生分辨率。

<img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102163003507.png" alt="image-20220102163003507" style="zoom:50%;" />

------

## 【笔记2】DLSS到底是什么技术？为何能提升游戏性能？有代价吗？

### 低分辨率的性能开销实现高分辨率的画面的表现

* 游戏性能的开销是跟着显示器的发展慢慢变高的，期间游戏本身开销也在上升。光追的加入更是大幅度提高了性能需求。

### 插值优化技术：

#### 棋盘渲染 Checkerboard Rendering Technique

* 最早需要迫切完成这个需求的不是pc，而是游戏主机。2016年索尼发布了PS4 Pro，这也是Playstation家族第一次在两代主机之间推出一个性能增强的版本。但PS4 Pro的推出，主要归功于4K电视的普及，其就是为了4k游戏而来。不过，PS4 Pro主要搭载了一个降频版的RX480，同样是GCN架构的PS4 Pro性能不过是原版PS4的两倍出头。可4K游戏大约需要4倍于原先的计算量，更何况原版RX480也无法满足4K游戏的需求。于是索尼引入了**棋盘渲染**（双立方插值）。
* 实际采样率不高，通过单帧信息插值。像毛发就会模糊，运动物体的边缘容易产生闪烁，这就是不同帧之间的锯齿。

<img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102171117482.png" alt="image-20220102171117482" style="zoom:50%;" />

#### 对比度自适应锐化 Fidelity CAS

#### 深度学习超级采样 DLSS

##### DLSS一代 

使用SM进行运算

<img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102171631559.png" alt="image-20220102171631559" style="zoom:50%;" />

<img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102171744211.png" alt="image-20220102171744211" style="zoom: 50%;" />

##### DLSS2.0 时域超采样、深度学习、图像重构

* AI视频插值和插帧：对于视频而言，通过某一帧前后的信息，是可以计算出每个像素精确的运动向量的。

<img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102172217115.png" alt="image-20220102172217115" style="zoom:50%;" />

* 但是游戏没有未来帧，只用过去帧插值则回到了棋盘渲染的问题，带来闪烁和鬼影。

* DLSS 2.0 用上了在超级计算机上数万张超高质量图片训练的神经网路来做启发式算法。

  <img src="C:\Users\曾\AppData\Roaming\Typora\typora-user-images\image-20220102172444529.png" alt="image-20220102172444529"  />

### 对比原生4K、PS4 Pro下棋盘渲染和DLSS 2.0的画质

* 看视频

* 2077：无法在4K光追全开的情况下跑到60fps，甚至30fps。只能降低渲染分辨率，或者用Fidelity CAS锐化
* 4K下的3070打开质量档DLSS2.0 vs 不开DLSS 3090

### DLSS2.0 问题

反射分辨率问题（水面）

游戏中的反射分辨率为了降低渲染压力，其实要低于整体渲染分辨率的。DLSS 2.0只能针对游戏整体的渲染做优化。但对于本来分辨率就更低的反射分辨率，通过DLSS 2.0 就会降到更低。同样的事情在体积光和体积雾上，在开启DLSS 2.0超级性能档时，灯关体积雾分辨率降低。

未来的游戏在开启DLSS时，让反射分辨率回到和渲染分辨率一致的水平，关闭DLSS的时候再降低反射分辨率换取性能。

DLSS 2.0 技术再相当大程度上降低了高分辨率、高画质游戏的配置门槛，在画质降低不明显的情况下非常有效提升了帧数。而相比于DLSS1.0，也有了更高的锐度和更好的细节表现。

------

## 【笔记3】GTC 2020: DLSS 2.0 - Image Reconstruction for Real-time Rendering with Deep Learning

### DLSS 2.0 offers several key enhancements over the original version:

* **Superior Image Quality**

  DLSS 2.0 offers image quality comparable to native resolution while **rendering only one quarter to one half of the pixels**. It employs new **temporal feedback techniques** for **sharper image** details and improved **stability** from frame to frame.

* **Great Scaling Across All GeForce RTX GPUs and Resolutions**

  A new AI network more efficiently uses **Tensor Cores** to execute **2X faster** than the original. This improves **frame rates** and eliminates previous **limitations on which GPUs, settings**, and **resolutions could be enabled**.

* **One Network For All Games** 

  The original DLSS required training the AI network for each new game. DLSS 2.0 trains using non-game-specific content, delivering a generalized network that works across games. This means faster game integrations, and ultimately more DLSS games.

* **Customizable Options**

  DLSS 2.0 offers users 3 image quality modes - Quality, Balanced, Performance - that control the game’s internal rendering resolution, with Performance mode enabling up to 4X super resolution (i.e. 1080p → 4K). This means more user choice, and even bigger performance boosts.

* DLSS 2.0 substantially boosts performance while maintaining --and in some cases improving-- image quality.

### Under the Hood

* Using our Neural Graphics Framework, [NGX](https://developer.nvidia.com/rtx/ngx), the DLSS deep neural network is trained on a [NVIDIA DGX-powered](https://www.nvidia.com/en-us/data-center/dgx-systems/) supercomputer.
* DLSS 2.0 has two primary inputs into the AI network:
  1. Low resolution, aliased images rendered by the game engine
  2. Low resolution, motion vectors from the same images -- also generated by the game engine

* Motion vectors tell us which direction objects in the scene are moving from frame to frame. We can apply these vectors to the previous high resolution output to estimate what the next frame will look like. We refer to this process as ‘temporal feedback,’ as it uses history to inform the future.

  <img src="https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/nvidia-dlss-2-0/nvidia-dlss-2-0-architecture-850px.jpg" alt="The NVIDIA DLSS 2.0 Architecture" style="zoom:50%;" />

* A special type of AI network, called a convolutional autoencoder, takes the low resolution current frame, and the high resolution previous frame, to determine on a pixel-by-pixel basis how to generate a higher quality current frame.
* During the training process, the output image is compared to an offline rendered, ultra-high quality 16K reference image, and the difference is communicated back into the network so that it can continue to learn and improve its results. This process is repeated tens of thousands of times on the supercomputer until the network reliably outputs high quality, high resolution images.
* Once the network is trained, NGX delivers the AI model to your GeForce RTX PC or laptop via Game Ready Drivers and OTA updates. With Turing’s Tensor Cores delivering up to 110 teraflops of dedicated AI horsepower, the DLSS network can be run in real-time simultaneously with an intensive 3D game. This simply wasn’t possible before Turing and Tensor Cores.

### DLSS 2.0 In Action

#### E.g Control

* While the original implementation of DLSS in *Control* boosted performance and provided great image quality across most scenes, it tended to struggle in areas with objects in motion. In contrast, DLSS 2.0 is able to handle these cases much more effectively as seen in the image of a spinning fan below.

[<img src="https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/control-nvidia-dlss-2-0-update/control-nvidia-dlss-2.0-comparison-004.png" alt="Control: Award Winning Game Updates To NVIDIA DLSS 2.0 and Releases First DLC" style="zoom:50%;" />](https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/control-nvidia-dlss-2-0-update/control-nvidia-dlss-2.0-comparison-004.png)

* The latest version of DLSS also improves image quality where the details are a bit more subtle. The following images show additional examples of improvements from the original version of DLSS to the updated version of DLSS 2.0.

  <img src="https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/control-nvidia-dlss-2-0-update/control-nvidia-dlss-2.0-comparison-001.png" alt="Control: Award Winning Game Updates To NVIDIA DLSS 2.0 and Releases First DLC" style="zoom: 50%;" />

  Elsewhere, text on seals and other detail is similarly improved, enhancing image quality and fidelity.

  <img src="https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/control-nvidia-dlss-2-0-update/control-nvidia-dlss-2.0-comparison-002.png" alt="Control: Award Winning Game Updates To NVIDIA DLSS 2.0 and Releases First DLC" style="zoom:50%;" />

* And flat textured game elements, such as posters and the map below, also see noticeable improvements to clarity and sharpness

  <img src="https://www.nvidia.com/content/dam/en-zz/Solutions/geforce/news/control-nvidia-dlss-2-0-update/control-nvidia-dlss-2.0-comparison-003.png" alt="Control: Award Winning Game Updates To NVIDIA DLSS 2.0 and Releases First DLC" style="zoom:50%;" />

### DLSS Continues to Learn

* With the **Turing architecture**, we set out to change gaming with two big leaps in graphics: **real-time ray tracing** and **NVIDIA DLSS**. Ray tracing brings next-generation **realism**, while DLSS boosts **framerates** to help you enjoy those stunning ray-traced visuals.
* Easier integration

## 【笔记4】[FUN科技] 冲！游戏帧率猛涨50%！DLSS技术就是强劲鸡血？

### 光线追踪

* 显卡通过运算调整光影达到逼真的效果。
* 光追之前：游戏一般是通过利用光栅化去提前渲染好画面（双缓冲）。开启光追帧率降低

### DLSS

* 显卡内置368个张量核心，对应DLSS技术

## 【笔记5】文刀秋二

“在图形领域，性能和画质绝对是成反比的，要想要更好的画质，一定要牺牲性能。而DLSS 2.0就是这种鱼和熊掌都给你的革命性技术。有了它，原生分辨率渲染将会变成过去式。“

NVIDIA是个神奇的公司。在以4K + 60Hz频率运行的渲染管线中每一帧运行一个神经网络这种想法乍一听是很疯狂，并且很有挑战性的。更不用说要用这种疯狂的想法真的实现出有商业价值的技术，其中要解决的“看似不可能”的技术问题真的数不胜数。用户好评的背后真的充满了我们研发过程中的泪水和血汗。然而我们似乎就是做到了。能对这种革命性的新技术做出贡献我个人也感觉非常幸运。”

## 参考资源

- [x] [Bilibili：DLSS到底是什么技术？为何能提升游戏性能？有代价吗？](https://www.bilibili.com/video/BV1Dy4y117BM?spm_id_from=333.999.0.0)

- [x] [Bilibili：【硬件科普】免费提升画质和帧数？详解DLSS2.0的工作原理与作用](https://www.bilibili.com/video/BV1PA41187g2?spm_id_from=333.999.0.0)

- [x] [Bilibili：【FUN科技】冲！游戏帧率猛涨50%！DLSS技术就是强劲鸡血？](https://www.bilibili.com/video/BV1S4411P7FZ?from=search&seid=12778510427660089974&spm_id_from=333.337.0.0)

- [ ] [SCI：An overview of current deep learned rendering technologies](https://www.webofscience.com/wos/alldb/full-record/INSPEC:20799965) 

  PDF： [An_Overview_of_Current_Deep_Learned_Rendering_Technologies.pdf](C:\Users\曾\Desktop\An_Overview_of_Current_Deep_Learned_Rendering_Technologies.pdf) 

- [x] [NVIDIA：DLSS 2.0](https://www.nvidia.com/en-us/geforce/news/nvidia-dlss-2-0-a-big-leap-in-ai-rendering/)

- [ ] [GTC 2020: DLSS 2.0 - Image Reconstruction for Real-time Rendering with Deep Learning](https://www.youtube.com/watch?v=d5knHzv0IQE) 

  PPT： [DLSS2.0.pdf](C:\Users\曾\Desktop\DLSS2.0.pdf) 

  文稿：[DLSS 2.0 - 基于深度学习的实时渲染图像重建](https://zhuanlan.zhihu.com/p/123642175)

- [ ]  [Machine Learning and Rendering.pdf](C:\Users\曾\Desktop\Machine Learning and Rendering.pdf) 

- [ ]  [Real-Time Rendering Fourth Edition.pdf](C:\Users\曾\Desktop\Real-Time Rendering Fourth Edition.pdf) 

- [x] [文刀秋二](https://www.zhihu.com/people/edliu/posts)

- [ ] [wiki DLSS](https://en.wikipedia.org/wiki/Deep_learning_super_sampling)


* [CSDN：图形图像渲染原理](https://blog.csdn.net/weixin_37637399/article/details/102366475?ops_request_misc=&request_id=&biz_id=102&utm_term=AI%E6%B8%B2%E6%9F%93%E6%96%B9%E6%B3%95&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-102366475.first_rank_v2_pc_rank_v29&spm=1018.2226.3001.4187)
* [CSDN：实时渲染和离线渲染的区别](https://blog.csdn.net/zipack/article/details/114957828?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-11-114957828.pc_agg_new_rank&utm_term=AI+%E6%B8%B2%E6%9F%93&spm=1000.2123.3001.4430)

