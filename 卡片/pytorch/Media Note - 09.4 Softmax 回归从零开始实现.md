---
media: https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4
---


![Softmax 回归从零开始实现 - 00:26](Softmax%20回归从零开始实现PT26.566S.webp) [00:26](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=26.566228#t=26.57) 导入数据
每次随机读256张图片
返回训练集和测试集的迭代器

![Softmax 回归从零开始实现 - 00:51](Softmax%20回归从零开始实现PT51.211S.webp) [00:51](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=51.21057#t=51.21) softmax的输入需要是向量
简单的拉成一个向量。会损失很多空间信息(留给卷积神经网络解决)
W:初始化为高斯随机的值。注意形状行数与列数。计算梯度true
b：每一个都需要便宜。所以它是一个长为10的向量

![Softmax 回归从零开始实现 - 02:37](Softmax%20回归从零开始实现PT2M37.691S.webp) [02:37](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=157.69096#t=02:37.69) 定义softmax操作回顾一下矩阵按照形状求和


![Softmax 回归从零开始实现 - 03:36](Softmax%20回归从零开始实现PT3M36.839S.webp) [03:36](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=216.838775#t=03:36.84) softmax公式
对矩阵的元素求指数
然后对维度为1求和，也就是消除第二个维度，因为是二维的矩阵。所以他是对每一行求和。
返回它每一个元素的指数除以所在行的指数和就是softmax回归函数

![Softmax 回归从零开始实现 - 04:35](Softmax%20回归从零开始实现PT4M35.336S.webp) [04:35](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=275.336027#t=04:35.34) 验证
softmax每个值为正，每个行为1

![Softmax 回归从零开始实现 - 05:44](Softmax%20回归从零开始实现PT5M44.576S.webp) [05:44](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=344.576002#t=05:44.58) 实现
-1是代表自动计算维度的大小。batchsize是256，所以X计算出来是一个(256,784)的矩阵
最终得到一个所有元素大于0，且行和为1的元素


![Softmax 回归从零开始实现 - 06:39](Softmax%20回归从零开始实现PT6M39.123S.webp) [06:39](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=399.122873#t=06:39.12) 交叉熵损失实现前的补充细节
给你一个预测值，拿出那个类别的真实预测值

![Softmax 回归从零开始实现 - 08:16](Softmax%20回归从零开始实现PT8M16.076S.webp) [08:16](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=496.075931#t=08:16.08) 交叉熵损失函数
拿到对应的损失

![Softmax 回归从零开始实现 - 09:16](Softmax%20回归从零开始实现PT9M16.573S.webp) [09:16](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=556.573466#t=09:16.57) 预测类别和真实类别的比较
每一行元素最大的小标存到y_hat里面
转换数据类型再作比较

![Softmax 回归从零开始实现 - 10:38](Softmax%20回归从零开始实现PT10M38.72S.webp) [10:38](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=638.719617#t=10:38.72) 计算模型再数据集上的精度
分类正确的样本数/总的样本数

![Softmax 回归从零开始实现 - 11:44](Softmax%20回归从零开始实现PT11M44.74S.webp) [11:44](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=704.739741#t=11:44.74) 

![Softmax 回归从零开始实现 - 12:19](Softmax%20回归从零开始实现PT12M19.602S.webp) [12:19](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=739.601761#t=12:19.60) 训练整个脚本

![Softmax 回归从零开始实现 - 14:36](Softmax%20回归从零开始实现PT14M36.781S.webp) [14:36](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=876.781104#t=14:36.78) 实现一个小动画的辅助函数


![Softmax 回归从零开始实现 - 14:57](Softmax%20回归从零开始实现PT14M57.463S.webp) [14:57](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=897.462894#t=14:57.46) 训练函数


![Softmax 回归从零开始实现 - 16:10](Softmax%20回归从零开始实现PT16M10.769S.webp) [16:10](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=970.768651#t=16:10.77) 

![Softmax 回归从零开始实现 - 16:35](Softmax%20回归从零开始实现PT16M35.432S.webp) [16:35](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=995.4322#t=16:35.43) 训练过程解析
训练精度，测试精度，损失

![Softmax 回归从零开始实现 - 17:47](Softmax%20回归从零开始实现PT17M47.946S.webp) [17:47](https://www.bilibili.com/video/BV1K64y1Q7wu/?p=4&t=1067.945866#t=17:47.95) 预测
