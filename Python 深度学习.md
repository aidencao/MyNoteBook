# Python 深度学习

## 2. 神经网络的数学基础

### 2.2 神经网络的数学表示

#### A.张量（Tensor）

以__维度（dimension）或轴（axis）__来区分张量，其中一个维度表示一个“坐标轴”，0D张量为单个数字，多个0D张量组成合并形成1D张量——向量，以此类推2D张量为矩阵、3D张量可看作多个矩阵组成的立方体。

PS：注意区分与多维向量的区别。
#### B.张量的关键属性

* 轴的个数（阶数，ndim）
* 形状  是一个**整元数组**，其中每个元素表示张量沿每个轴的元素大小
* 数据类型  张量中包含的数据类型

#### C.批量轴/批量维度

张量的**第一个轴**，用于表示样本数目，在进行深度学习时通常会进行拆分

#### D.常用的张量类型

* 向量数据 2D，形状为（samples，features）
* 时间序列或其他序列数据 3D，形状为（samples，timesteps，features）
* 图像 4D，形状为（samples，height，width，channels）或（samples，channels，height，width）
* 视频 5D，形状为（samples，frames，height，width，channels）或（samples，frames，channels，height，width）

### 2.3 张量的运算

#### A.张量的广播

在进行高维张量和低维张量的运算时，会自动将低维张量增加新轴，**并沿着新轴不断重复**，使得**形状**与高维张量相同。

#### B.点积运算
相当于降维，相当于将两个张量的某个相同大小的维度的元素一一相乘，最后相加。

#### C.张量变形
改变**张量的行和列**,以获取需要的形状，但是变形**不会改变元素个数**。
>**张量转置**：行列互换

## 3.神经网络入门

### 3.1 神经网络剖析
#### 3.1.1 层
A. 密集连接层(全连接层): 用于2D张量 Dense
B. 循环层: 用于3D张量 例如LSTM层
C. 二维卷积层: 用于4D张量 例如Conv2D

### 3.2 Keras入门
#### 3.2.2 Keras开发流程
* 定义训练数据
* 定义网络
>1.使用Sequential类进行线性堆叠
>2.函数式API
* 配置学习过程（损失函数、优化器、监控指标）
* 进行学习

### 3.4 电影评论分类：二分类问题
#### A. Dense层堆叠类型的网络构建
1.网络有多少层
2.每层有多少个**隐藏单元**
>隐藏单元越多,学习自由度越高,计算代价会越大,但过高会导致过拟合(调参的一部分)

3.激活函数的选择

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjI5ODYxNTMyLDIyOTg2MTUzMiwtMTQ1Nz
QwMDg3LDEzMzI1NDE4MzcsMTAzNzU2ODA0NCwyNzY5MzY5NDAs
LTExNjE5OTE1NjksOTMxOTIxMzM4XX0=
-->