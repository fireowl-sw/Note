---
media: https://www.bilibili.com/video/BV1pm42137bR/
---
DECK: Ros2::1.4.5 Linux基础之环境变量

#### 查看当前终端配置的ROS版本
- [01:57](https://www.bilibili.com/video/BV1pm42137bR/?t=117.266873#t=01:57.27) 
echo 输出打印指令
- 加入$符号会在环境变量中寻找 ROS版本ROS_VERTION。当前是ROS2
- echo $ROS_DISTRO 发行版本名
- ![《ROS 2机器人开发从入门到实践》 1.4.5 Linux基础之环境变量 - 03:57|50](《ROS%202机器人开发从入门到实践》%201.4.5%20Linux基础之环境变量PT3M57.766S.png) [03:57](https://www.bilibili.com/video/BV1pm42137bR/?t=237.765866#t=03:57.77) printenv打印所有环境变量
<!--ID: 1742976465535-->


#### 环境变量的作用
- [04:31](https://www.bilibili.com/video/BV1pm42137bR/?t=272.432782#t=04:31.00) 
ros2 run turtlesim turtlesim_node
ros2 run 功能包名 可执行文件名
printenv可以找到环境变量的值
下面是运行的寻找逻辑
- [08:16](https://www.bilibili.com/video/BV1pm42137bR/?t=496.353936#t=08:16.35) 
找AMENT_PREFIX_PATH得到路径
lib文件夹下有功能名包，对应的有可执行文件
- ![《ROS 2机器人开发从入门到实践》 1.4.5 Linux基础之环境变量 - 10:17|50](《ROS%202机器人开发从入门到实践》%201.4.5%20Linux基础之环境变量PT10M17.315S.png) [10:17](https://www.bilibili.com/video/BV1pm42137bR/?t=617.314827#t=10:17.31) 可以用环境变量替换来运行
- ![《ROS 2机器人开发从入门到实践》 1.4.5 Linux基础之环境变量 - 11:15|50](《ROS%202机器人开发从入门到实践》%201.4.5%20Linux基础之环境变量PT11M15.614S.png) [11:15](https://www.bilibili.com/video/BV1pm42137bR/?t=675.614359#t=11:15.61) 
<!--ID: 1742976465545-->



#### 修改环境变量路径
- [12:13](https://www.bilibili.com/video/BV1pm42137bR/?t=733.025486#t=12:13.03) 
export 修改环境变量名字
export AMENT_PREFIX_PATH=/opt/ros/
验证命令
printenv | grep AMENT
- ![《ROS 2机器人开发从入门到实践》 1.4.5 Linux基础之环境变量 - 13:25|50](《ROS%202机器人开发从入门到实践》%201.4.5%20Linux基础之环境变量PT13M25.392S.png) [13:25](https://www.bilibili.com/video/BV1pm42137bR/?t=805.391845#t=13:25.39) 
修改后就无法使用ros2 run来运行了
- [15:46](https://www.bilibili.com/video/BV1pm42137bR/?t=946.250596#t=15:46.25) 临时修改，打开新终端就恢复了(由于终端启动的默认脚本 .bashrc)(ls -a可以找到.开头的隐藏文件)
> 遇到package ‘’ not found 就去找环境变量，根据路径找对应文件
<!--ID: 1742976465553-->


#### .bashrc的内容
- ![《ROS 2机器人开发从入门到实践》 1.4.5 Linux基础之环境变量 - 20:27|50](《ROS%202机器人开发从入门到实践》%201.4.5%20Linux基础之环境变量PT20M27.808S.png) [20:27](https://www.bilibili.com/video/BV1pm42137bR/?t=1227.807758#t=20:27.81) 启动后source设置了环境变量
- 所以如果没有的话可以通过nano/vim自己进行设置
<!--ID: 1742976465564-->

