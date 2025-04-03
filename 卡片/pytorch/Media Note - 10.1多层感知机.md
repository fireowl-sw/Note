---
media: https://www.bilibili.com/video/BV1hh411U7gn/?p=2
---
![多层感知机 - 00:21](多层感知机PT21.396S.webp) [00:21](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=21.396172#t=21.40) 如何解决XOR问题
![多层感知机 - 01:09](多层感知机PT1M9.051S.webp) [01:09](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=69.051352#t=01:09.05) 蓝色的线1，3 +；2，4 -
黄色的线 1，2 +；3，4 -
对两个结果做异或
![多层感知机 - 02:35](多层感知机PT2M35.155S.webp) [02:35](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=155.155087#t=02:35.16) 右下角的图
![多层感知机 - 03:16](多层感知机PT3M16.725S.webp) [03:16](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=196.724751#t=03:16.72) 加入了一个隐藏层
隐藏层的大小是一个超参数

![多层感知机 - 04:16](多层感知机PT4M16.673S.webp) [04:16](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=256.672593#t=04:16.67) 具体做法
σ是激活函数
h是长为m的向量，作为输入进入输出层

![多层感知机 - 06:40](多层感知机PT6M40.798S.webp) [06:40](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=400.798399#t=06:40.80) 为什么需要非线性的激活函数
因为线性的话它依旧等价于单层的感知机
最简单那的线性模型


![多层感知机 - 08:28](多层感知机PT8M28.598S.webp) [08:28](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=508.598413#t=08:28.60) sigmoid激活函数



![多层感知机 - 09:43](多层感知机PT9M43.106S.webp) [09:43](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=583.105717#t=09:43.11) Tanh激活函数
将输入投影到(-1,1)

![多层感知机 - 10:32](多层感知机PT10M32.012S.webp) [10:32](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=632.011556#t=10:32.01) 最常用的激活函数
max(x,0)
优点：计算很快
指数运算是一件很贵的事情。做一次相当于做100次乘法 

![多层感知机 - 13:13](多层感知机PT13M13.331S.webp) [13:13](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=793.331188#t=13:13.33) 多类
softmax就是把所有的输入拉到(0,1)的区域类，使得y1+...+yk为1。变成一个概率。

![多层感知机 - 14:07](多层感知机PT14M7.154S.webp) [14:07](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=847.153895#t=14:07.15) 多层感知机和softmax的区别就是加入了中间这一层隐藏层

![多层感知机 - 14:28](多层感知机PT14M28.237S.webp) [14:28](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=868.237005#t=14:28.24) 多层分类和感知机的单层分类的区别就是输出层多出了个k类
对输出要做一个softmax

![多层感知机 - 15:27](多层感知机PT15M27.652S.webp) [15:27](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=927.651706#t=15:27.65) 多隐藏层
每一个隐藏层都有一个自己的W，b

![多层感知机 - 17:35](多层感知机PT17M35.253S.webp) [17:35](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=1055.253256#t=17:35.25) m1设的稍微大一点
经验：假设数据比较难。相对于单隐藏层多隐藏层的m1稍微小一点，m2比m1小一点......
最下一层m1稍微胖一点没关系，防止压缩太大丢失信息

![多层感知机 - 21:34](多层感知机PT21M34.281S.webp) [21:34](https://www.bilibili.com/video/BV1hh411U7gn/?p=2&t=1294.28084#t=21:34.28) 