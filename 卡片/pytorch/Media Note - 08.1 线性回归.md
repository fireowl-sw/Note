---
media: https://www.bilibili.com/video/BV1PX4y1g7KC/
---
DECK: pytorch::08.1 线性回归

线性回归
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 03:29|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT3M29.051S.png) [03:29](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=209.050873#t=03:29.05) 房价的线性回归模型
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 04:20|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT4M20.222S.png) [04:20](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=260.221742#t=04:20.22) 
线性模型可以看成一个单层的神经网络（权重层为1）

神经网络的来源
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 06:14|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT6M14.553S.png) [06:14](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=374.552896#t=06:14.55) 神经网络的源头

衡量预估质量
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 07:38|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT7M38S.png) [07:38](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=458.000404#t=07:38.00) 房价区别越小模型质量越高，区别越大模型质量越低

训练数据（权重，偏差）
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 08:43|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT8M43.488S.png) [08:43](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=523.488387#t=08:43.49) 

参数学习
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 10:31|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT10M31.824S.png) [10:31](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=631.824416#t=10:31.82) 

显示解
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 12:06|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT12M6.593S.png) [12:06](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=726.593314#t=12:06.59) 
- 凸函数的性质是最优解满足图中的形式
总结
- ![08 线性回归 + 基础优化算法【动手学深度学习v2】 - 14:01|50](08%20线性回归%20+%20基础优化算法【动手学深度学习v2】PT14M1.491S.png) [14:01](https://www.bilibili.com/video/BV1PX4y1g7KC/?t=841.490696#t=14:01.49) 


#### 公式总结
输入向量
$\mathbf{x} = [x_1, x_2, \ldots, x_n]^T$
权重向量，标量偏差
$\mathbf{w} = [w_1, w_2, \ldots, w_n]^T$，b
输出公式（标量形式）
$y = w_1x_1 + w_2x_2 + \ldots + w_nx_n + b$
输出公式（向量形式）
$y=\langle\mathbf{w},\mathbf{x}\rangle + b$
平方损失函数(真实值-损失值)
$\ell(y,\hat{y})=\frac{1}{2}(y - \hat{y})^2$
权重和偏差(训练数据)
$\mathbf{X} = [\mathbf{x}_1,\mathbf{x}_2,\cdots,\mathbf{x}_n]^T$
$\mathbf{y} = [y_1,y_2,\cdots,y_n]^T$
训练损失$\ell(\mathbf{X},\mathbf{y},\mathbf{w},b)=\frac{1}{2n}\sum_{i = 1}^{n}(y_i-\langle\mathbf{x}_i,\mathbf{w}\rangle-b)^2=\frac{1}{2n}\|\mathbf{y}-\mathbf{X}\mathbf{w}-b\|^2$
最小化损失来学习参数
$\mathbf{w}^*, \mathbf{b}^* = \underset{\mathbf{w,b}}{\arg\min} \ell(\mathbf{X},\mathbf{y},\mathbf{w},\mathbf{b})$
将偏差加入权重$\mathbf{X} \leftarrow [\mathbf{X}, 1]$ $\mathbf{w} \leftarrow \begin{bmatrix} \mathbf{w} \\ b \end{bmatrix}$
$\ell(\mathbf{X},\mathbf{y},\mathbf{w})=\frac{1}{2n}\|\mathbf{y}-\mathbf{Xw}\|^{2}$
$\frac{\partial}{\partial \mathbf{w}} \ell(\mathbf{X}, \mathbf{y}, \mathbf{w})=\frac{1}{n}(\mathbf{y}-\mathbf{X} \mathbf{w})^{T}$
损失是凸函数最优解满足
$\frac{\partial}{\partial \mathbf{w}} \ell(\mathbf{X}, y, \mathbf{w}) = 0$
$\Leftrightarrow \frac{1}{n}(\mathbf{y}-\mathbf{X} \mathbf{w})^{T} \mathbf{X} = 0$
$\Leftrightarrow \mathbf{w}^{*}=\left(\mathbf{X}^{T} \mathbf{X}\right)^{-1} \mathbf{X} \mathbf{y}$
<!--ID: 1743049897527-->

