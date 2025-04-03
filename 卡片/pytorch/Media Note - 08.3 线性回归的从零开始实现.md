---
media: https://www.bilibili.com/video/BV1PX4y1g7KC?p=3
---
DECK: pytorch::08.3 线性回归的从零开始实现

不使用任何深度学习算法，使用最简单的进行理解线性回归

### 线性回归代码解释

#### ![线性回归的从零开始实现 - 00:46|50](线性回归的从零开始实现PT46.937S.webp) [00:44](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=46.93724#t=44) 导包
- d2l里面的torch里是实现过的算法函数
- %matplotlib inline 默认嵌入到notebook里面
- random包：随机梯度下降和初始化权重
<!--ID: 1743047000151-->



#### ![线性回归的从零开始实现 - 01:33|50](线性回归的从零开始实现PT1M33.304S.webp) [01:32](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=93.303697#t=01:32.30) 构造很小的人造数据集
- synthetic_data(w, b, 样本数量)生成合成数据。它创建一个包含随机特征的矩阵`X`，并根据给定的权重向量`w`、偏差`b`以及添加一些噪声来生成目标向量`y`。
- $f(x)=\frac{1}{\sigma\sqrt{2\pi}}e^{-\frac{(x - \mu)^2}{2\sigma^2}}$正态分布 $\mu$ 是均值，$\sigma$ 是标准差。
- `X = torch.normal(0, 1, (num_examples, len(w)))`使用均值为0、标准差为1的正态分布生成一个形状为`(num_examples, len(w))`的随机张量`X`。这里`len(w)`表示特征的数量，`num_examples`表示样本数量。$\varphi(x)=\frac{1}{\sqrt{2\pi}}e^{-\frac{x^{2}}{2}}$
- `y = torch.matmul(X, w) + b`通过矩阵乘法`torch.matmul(X, w)`将特征矩阵`X`与权重向量`w`相乘，并加上偏差`b`来计算目标向量`y`的无噪声版本。
- `y += torch.normal(0, 0.01, y.shape)`使用均值为0、标准差为0.01的正态分布生成噪声，形状与y一样。并将其添加到目标向量`y`中，使其更接近真实世界中的数据（带有一定的随机性和误差
- `y.reshape((-1, 1))`将`y`重塑为列向量
<!--ID: 1743047000163-->

#### ![线性回归的从零开始实现 - 03:06|50](线性回归的从零开始实现PT3M6.231S.webp) [03:06](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=186.231402#t=03:06.23) 可视化训练样本
图中代码有点错误。
`d21.plt.scatter(features[:, 1].detach().numpy(), labels.detach().numpy(), 1);`
- 从`features`数据中提取第二列（索引从0开始计数所以`[:, 1]`表示第二列）的数据，并将其从计算图中分离（`detach`）然后转换为`numpy`数组格式，作为散点图的`x`坐标数据。
- `labels.detach().numpy()`：将`labels`数据从计算图中分离（`detach`）然后转换为`numpy`数组格式，作为散点图的`y`坐标数据。
<!--ID: 1743047401682-->


#### ![线性回归的从零开始实现 - 03:52|50](线性回归的从零开始实现PT3M52.591S.webp) [03:52](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=232.59079#t=03:52.59) 分批量读取函数
- **按批次生成数据**
- 这段代码通过循环，每次从打乱后的索引列表中取出`batch_size`个索引（最后一个批次可能不足`batch_size`个），并使用这些索引从`features`和`labels`中获取相应的批次数据
- 通过`yield`关键字将批次数据以生成器（generator）的形式返回。这样在外部使用`for`循环调用`data_iter`函数时，可以逐个获取每个批次的数据。
- 生成器使用 `yield` 关键字来定义，当函数执行到 `yield` 语句时，它会暂停执行并返回一个值，下次调用该生成器时，会从上次暂停的地方继续执行。
-  PyTorch 中的张量操作更加高效，并且可以利用 GPU 进行加速，所以需要将indices子列表转换为 PyTorch 张量，也就是使用 `torch.tensor` 函数进行转换，然后将转换后的张量赋值给 `batch_indices`。
<!--ID: 1743048293988-->


#### ![线性回归的从零开始实现 - 06:47|50](线性回归的从零开始实现PT6M47.885S.webp) [06:47](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=407.885499#t=06:47.89) 初始化模型参数
对应的线性回归数学公式如下
输入向量
$\mathbf{x} = [x_1, x_2, \ldots, x_n]^T$
权重向量，标量偏差
$\mathbf{w} = [w_1, w_2, \ldots, w_n]^T$，b
输出公式（标量形式）
$y = w_1x_1 + w_2x_2 + \ldots + w_nx_n + b$
输出公式（向量形式）
$y=\langle\mathbf{w},\mathbf{x}\rangle + b$
>requires_grad代表存入梯度计算中
<!--ID: 1743073077197-->


#### ![线性回归的从零开始实现 - 08:03|50](线性回归的从零开始实现PT8M3.158S.webp) [08:03](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=483.158439#t=08:03.16) 定义损失函数
平方损失函数(真实值-损失值)
$\ell(y,\hat{y})=\frac{1}{2}(y - \hat{y})^2$
这里的损失函数没有求均值
<!--ID: 1743075888591-->


#### ![线性回归的从零开始实现 - 08:45|50](线性回归的从零开始实现PT8M45.176S.webp) [08:45](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=525.175976#t=08:45.18) 定义优化算法sgd
$\mathbf{w}_{t}=\mathbf{w}_{t - 1}-\eta\frac{\partial\ell}{\partial\mathbf{w}_{t - 1}}$
- 梯度会存在.grad里面
- /bach_size求一下均值
- lr是学习率
- params包含了w和b
- param.grad.zero_()把梯度设置成0，这样下一次计算梯度就不会和这一次相关
<!--ID: 1743075888605-->



####  ![线性回归的从零开始实现 - 10:20|50](线性回归的从零开始实现PT10M20.37S.webp) [10:20](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=620.370366#t=10:20.37) 训练过程
超参数：lr学习率；num_epochs扫3遍数据；
net=模型；loss=损失
赋值方便后面更换模型
with torch.no_grad()表示不需要计算梯度
然后将整个feature放进去计算损失，打印出来康康
<!--ID: 1743075888614-->



 ![线性回归的从零开始实现 - 12:45|50](线性回归的从零开始实现PT12M45.035S.webp) [12:45](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=765.035038#t=12:45.04) 查看真实数据和人工数据的区别
真实与训练做差打印


- ![线性回归的从零开始实现 - 13:35|50](线性回归的从零开始实现PT13M35.004S.webp) [13:35](https://www.bilibili.com/video/BV1PX4y1g7KC?p=3&t=815.004353#t=13:35.00) 查看改变超参数的效果


