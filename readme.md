# Emotional Talking Head Generation项目

本项目旨在梳理和总结本人在**Emotional Talking Head Generation**方向的学习和工作

"Emotions shape ourselves, determine who we are, and affect our daily behavior"

## 方向概述

个人理解：Talking Head Generation这个方向在于生成真实的人脸图像或者连续真实的人脸视频帧，目前已经有一定的发展；然而，可以精确控制**Face Emotion、Lip Movement、Talking Style、Blink、Regional Facial Movement**这些人脸细节的方法仍在探索中，因此产生**Emotional Talking Head Generation**这条道路。目前，主要是以**3DMM**和**GAN**作为核心，以**Blend、Alignment**等等方法作为辅助去探索新的框架和优化约束方法。



<div>			<!--块级封装-->
    <center>	<!--将图片和文字居中-->
    <img src="https://raw.githubusercontent.com/guohua-zhang/Emotional-Talking-Head-Generation/main/imgs/img1.png"
         alt="无法显示Example"
         style="zoom:2"/>
    <br>		<!--换行-->
    <b>
    Example	From NED（CVPR2022）<!--标题-->
    </center>
</div>





## 更新列表-2023.03.26

- [ ] 方向脉络梳理
- [ ] 复现工作
  - [ ] GANmut（CVPR2021）
  - [ ] IC-face（WACV2020）
  - [ ] DSM（ECCV2022）
- [ ] Our work



## 一、方向脉络梳理

**ing**..............................



## 二、复现工作

## （1）参考工作

https://www.nature.com/articles/s42256-020-00280-0.epdf?sharing_token=8UEdDpr-K7UpoDi5SYjGLtRgN0jAjWel9jnR3ZoTv0NmJm5LtKLATZX-wg4Cg96PU_Xagw0dC67imfvbYZzOaFRYUs-6qIlabUXidsXjQRkYDNWUaArHiGy8zxyz2DozptfHYg3G_HumDAHYUwgV2PRTjKDd-8LKGzbMstnxIxY%3D

https://github.com/face-analysis/emonet

https://github.com/michaildoukas/head2head

## （2）复现工作

### 1、DSM

由于本论文作者没有开源代码，本人只能尝试按照论文中描述的细节去尽可能地还原效果

#### a、VA值获取部分

参考Emonet论文：https://github.com/face-analysis/emonet

#### b、3DMM——Exp50向量部分

参考head2head++：https://github.com/michaildoukas/head2head

#### c、Expression Decoder部分

参考原论文中详细描述部分

##### c1、模型实质

训练出2D的人脸VA向量到3D表情向量exp50的映射（此处选用了DECA作为人脸重建方法，和原论文中的exp30有不同，但本质思想都是一样的）

是一个person-specific的模型映射，需要针对不同object进行训练

##### c2、网络结构

6层的fully connected layers：4096, 2048, 1024, 512, 128 and 64

激活函数：relu

技巧：dropout

##### c3、训练细节

训练率：e-3

batchsize：32

优化器：Adam

epoch：1000



## Reference

**Thanks to：**



